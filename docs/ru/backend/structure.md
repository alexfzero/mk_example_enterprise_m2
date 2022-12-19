# Структура

В этом разделе будет рассмотрена структура проекта, включая стандартное содержимое каждого App Django, а также исходные коды в качестве примера.

## Файловая структура

После клонирования репозитория с github вы можете перейти в каталог и увидеть следующую структуру:

![after git](../assets/git.png)

Папка "be_kursach" содержит основной код проекта:

![files](../assets/files.png)

В этом каталоге папки «contacts», «orders», «references» и «temps» являются App Django и содержат подобную структуру:

![png](../assets/app.png)

Коротко о функциях App Django:

- views - здесь размещается логика приложения. А также запрашивается информация у указанной модели, расположенной в директории "__models__";
- serializer - сериализаторы преобразуют информацию, хранящуюся в базе данных и определенную с помощью моделей Django, в формат, который легко и эффективно передается через API;
- urls - устанавливает ассоциации url-адресов с "__views__".

## Типичное приложение

Ниже приведен код с созданием функционала для простого App django.

### Models

Веб-приложения Django получают доступ к данным и управляют ими через объекты Python, называемые моделями. Модели определяют структуру хранимых данных, включая типы полей и, возможно, их максимальный размер, значения по умолчанию, параметры раскрывающегося списка, текст справки для документации, текст меток для форм и т. д.

``` py linenums="1" title="order.py"
from django.db.models import Model
from django.db.models.fields import CharField, IntegerField, DateField
from django.db.models.fields.related import ForeignKey
from django.db.models.deletion import CASCADE

from contacts.models import ExtendUser, Organization
from references.models import Contract


class PurchaseOrder(Model):
    order_number = CharField(max_length=30, unique=True)
    provider = ForeignKey(Organization, related_name='orders', on_delete=CASCADE)
    contact_person = ForeignKey(ExtendUser, related_name='contact_orders', on_delete=CASCADE)
    order_reg_date = DateField(auto_now_add=True)
    date_arrival = DateField()
    quantity = IntegerField()
    price = IntegerField()
    contract_number = ForeignKey(Contract, related_name='contract_orders', on_delete=CASCADE)
    purchase_manager = ForeignKey(ExtendUser, related_name='manager_orders', on_delete=CASCADE)
    vat = IntegerField()
    summary = CharField(max_length=255)

    def __str__(self):
        return f"{self.order_number}"

```


### Serializers

Эта запись предоставляет возможность управлять всеми атрибутами модели PurchaseOrder.

``` py linenums="1" title="order.py"
from rest_framework.serializers import ModelSerializer

from ...models.order import PurchaseOrder


class SuperUserPurchaseOrderSerializer(ModelSerializer):
    class Meta:
        model = PurchaseOrder
        fields = '__all__'
```


### Views

Приведенный ниже код обрабатывает запросы на определенные URL-адреса в соответствии с моделью PurchaseOrder и правами, определенными в классе IsGlobalAdminPermission. Затем он передает данные указанным сериализаторам для обработки и возвращает ответ.

``` py linenums="1" title="order.py"
from rest_framework.viewsets import ModelViewSet

from ...models.order import PurchaseOrder
from contacts.permissions import IsGlobalAdminPermission
from ...serializers.superuser import SuperUserPurchaseOrderSerializer


class SuperUserPurchaseOrderViewSet(ModelViewSet):
    queryset = PurchaseOrder.objects.all()
    serializer_class = SuperUserPurchaseOrderSerializer
    permission_classes = [IsGlobalAdminPermission]
```

### URLs

URL-адреса определяют шаблон для получения запросов извне к приложению. После сопоставления запроса и шаблона django запускает указанный view.

``` py linenums="1" title="superuser.py"
from django.urls import path, include

from rest_framework.routers import SimpleRouter

from ..views.superuser import SuperUserPurchaseOrderViewSet

orders_routers = SimpleRouter()
orders_routers.register(prefix='orders', viewset=SuperUserPurchaseOrderViewSet, basename='orders')

urlpatterns = [
    path('', include(orders_routers.urls))
]
```
