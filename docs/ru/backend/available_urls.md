# Доступные URL-адреса

Этот раздел содержит доступные URL-адреса, реализованные для управления моделями.

## Модель ExtendUser

``` json
[
	{
	    "name": "super|contacts|users-list",
	    "namespace": "super:contacts",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/contacts/users/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/contacts/users/"
		}
	    ]
	},
	{
	    "name": "super|contacts|users-detail",
	    "namespace": "super:contacts",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/contacts/users/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/contacts/users/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/contacts/users/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/contacts/users/<id>/"
		}
	    ]
	}
]
```

## Модель Organization

``` json
[
	{
	    "name": "super|contacts|organizations-list",
	    "namespace": "super:contacts",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/contacts/organizations/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/contacts/organizations/"
		}
	    ]
	},
	{
	    "name": "super|contacts|organizations-detail",
	    "namespace": "super:contacts",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/contacts/organizations/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/contacts/organizations/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/contacts/organizations/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/contacts/organizations/<id>/"
		}
	    ]
	}
]
```

## Модель PurchaseOrder

``` json
[
	{
	    "name": "super|orders|orders-list",
	    "namespace": "super:orders",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/orders/orders/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/orders/orders/"
		}
	    ]
	},
	{
	    "name": "super|orders|orders-detail",
	    "namespace": "super:orders",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/orders/orders/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/orders/orders/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/orders/orders/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/orders/orders/<id>/"
		}
	    ]
	}
]
```

## Модель Contract

``` json
[
	{
	    "name": "super|references|contracts-list",
	    "namespace": "super:references",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/references/contracts/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/references/contracts/"
		}
	    ]
	},
	{
	    "name": "super|references|contracts-detail",
	    "namespace": "super:references",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/references/contracts/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/references/contracts/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/references/contracts/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/references/contracts/<id>/"
		}
	    ]
	}
]
```

## Модель FlowFunds

``` json
[
	{
	    "name": "super|references|funds-list",
	    "namespace": "super:references",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/references/funds/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/references/funds/"
		}
	    ]
	},
	{
	    "name": "super|references|funds-detail",
	    "namespace": "super:references",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/references/funds/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/references/funds/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/references/funds/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/references/funds/<id>/"
		}
	    ]
	}
]
```

## Модель Storage

``` json
[
	{
	    "name": "super|references|storages-list",
	    "namespace": "super:references",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/references/storages/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/references/storages/"
		}
	    ]
	},
	{
	    "name": "super|references|storages-detail",
	    "namespace": "super:references",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/references/storages/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/references/storages/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/references/storages/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/references/storages/<id>/"
		}
	    ]
	}
]
```

## Модель StorageOperation

``` json
[
	{
	    "name": "super|references|operations-list",
	    "namespace": "super:references",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/references/operations/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/references/operations/"
		}
	    ]
	},
	{
	    "name": "super|references|operations-detail",
	    "namespace": "super:references",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/references/operations/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/references/operations/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/references/operations/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/references/operations/<id>/"
		}
	    ]
	}
]
```

## Модель Status

``` json
[
	{
	    "name": "super|temps|positions-list",
	    "namespace": "super:temps",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/temps/positions/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/temps/positions/"
		}
	    ]
	},
	{
	    "name": "super|temps|positions-detail",
	    "namespace": "super:temps",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/temps/positions/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/temps/positions/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/temps/positions/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/temps/positions/<id>/"
		}
	    ]
	}
]
```

## Модель Department

``` json
[
	{
	    "name": "super|temps|departments-list",
	    "namespace": "super:temps",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/temps/departments/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/temps/departments/"
		}
	    ]
	},
	{
	    "name": "super|temps|departments-detail",
	    "namespace": "super:temps",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/temps/departments/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/temps/departments/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/temps/departments/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/temps/departments/<id>/"
		}
	    ]
	}
]
```

## Модель Position

``` json
[
	{
	    "name": "super|temps|statuses-list",
	    "namespace": "super:temps",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/temps/statuses/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/temps/statuses/"
		}
	    ]
	},
	{
	    "name": "super|temps|statuses-detail",
	    "namespace": "super:temps",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/temps/statuses/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/temps/statuses/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/temps/statuses/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/temps/statuses/<id>/"
		}
	    ]
	}
]
```

## Модель OperationType

``` json
[
	{
	    "name": "super|temps|operations-list",
	    "namespace": "super:temps",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "list",
		    "method": "get",
		    "pattern": "/super/temps/operations/"
		},
		{
		    "action": "create",
		    "method": "post",
		    "pattern": "/super/temps/operations/"
		}
	    ]
	},
	{
	    "name": "super|temps|operations-detail",
	    "namespace": "super:temps",
	    "parameters": [],
	    "is_parameterize": false,
	    "methods": [
		{
		    "action": "retrieve",
		    "method": "get",
		    "pattern": "/super/temps/operations/<id>/"
		},
		{
		    "action": "update",
		    "method": "put",
		    "pattern": "/super/temps/operations/<id>/"
		},
		{
		    "action": "partial_update",
		    "method": "patch",
		    "pattern": "/super/temps/operations/<id>/"
		},
		{
		    "action": "destroy",
		    "method": "delete",
		    "pattern": "/super/temps/operations/<id>/"
		}
	    ]
	}
]
```
