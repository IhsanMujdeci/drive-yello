# drive-yello
CRUD system for orders. Calultes estimated delivery time

## Order Schema
```
{
    delivery: {
        textual: String,
        lat: String,
        long: String
    },
    pickup: {
        textual: String,
        lat: String,
        long: String
    },
    assignedTo: ID
    restautrant: String,
    private: Boolean,
    createdAt: Date,
    deliveryAt: Date
}
```

## Put Orders

`POST /orders`

## Get Order

`GET /orders/:id`

**Reponse**

```
{
    delivery: {
        textual: String,
        lat: String,
        long: String
    },
    pickup: {
        textual: String,
        lat: String,
        long: String
    },
    assignedTo: ID
    restautrant: String,
    private: Boolean,
    createdAt: Date,
    deliveryAt: Date
}
```

## Get Orders

`GET /orders`

**e.g:** `GET /orders/?createdAt=asc&items=10&page=2` 

Default behviour displays newest to oldest and shows all results possible

**Query Parameters:**

| name       | Description | Type|
| --------   | --------    | --------      |
| createdAt  | Sory by time created At     | `enum["asc", "dec"]` |
| deliveryAt | Sory by delivery time       | `enum["asc", "dec"]` |
| items      | How many orders per page    | `Number`            |
| page       | Which page of orders        | `Number`            |

**Response**
```
[
    ...{
        delivery: {
            textual: String,
            lat: String,
            long: String
        },
        pickup: {
            textual: String,
            lat: String,
            long: String
        },
        assignedTo: ID
        restautrant: String,
        private: Boolean,
        createdAt: Date,
        deliveryAt: Date
    }
]
```

## Patch Order

`PATCH /orders/:id`

## Auth

`GET /login`

**Response**
```
{
    JWTString
}
```
