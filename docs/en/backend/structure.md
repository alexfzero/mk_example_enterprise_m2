# Structure

This section will look at the structure of the project, including the standard content of each App Django, as well as the source codes as an example.

## File structure

After cloning the repository from github, you can navigate to the directory and see the following structure:

![after git](../assets/git.png)

Folder "be_kursach" contains the main project code:

![files](../assets/files.png)

In this directory, folders 'contacts', 'orders', 'references' and 'temps' are Django App and contain a similar structure:

![png](../assets/app.png)

Short about the functions of the App:

- view - application logic is placed here. It also requests information from the specified model located in the "__models__" directory;
- serializers - converts information stored in a database and defined using Django models into a format that is easily and efficiently passed through an API;
- urls - sets associations of url addresses with "__views__".

## Typical App

Below is the code with creating functionality for a simple django App

### Models

Django web applications access and manage data through Python objects called models. Models define the structure of the stored data, including field types and possibly their maximum size, default values, picklist options, help text for documentation, label text for forms, and so on.

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

This entry provides the ability to manage all the attributes of the PurchaseOrder model.

``` py linenums="1" title="order.py"
from rest_framework.serializers import ModelSerializer

from ...models.order import PurchaseOrder


class SuperUserPurchaseOrderSerializer(ModelSerializer):
    class Meta:
        model = PurchaseOrder
        fields = '__all__'
```


### Views

The code below processes requests for certain URLs in accordance with the PurchaseOrder model and the rights defined in the IsGlobalAdminPermission class. Then it transfers the data to the specified serializers for processing and returns the answer.

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

Urls define a pattern for receiving requests from outside to the application. After matching the request and the pattern, django runs the specified view.

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
