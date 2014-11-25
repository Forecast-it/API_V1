#Roles

##Get Roles

* `GET /roles` Returns all roles.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the role|
|id | Integer|
|name | String|
|description | String|
|internalCostPrice | Decimal|
|externalCostPrice | Decimal|

###Sample JSON Response
```json
[
   {
      "url":"https://api.forecast.it/api/v1/roles/1",
      "id":1,
      "name":"Developer",
      "description":"Developer resources",
      "internalCostPrice":110.00,
      "externalCostPrice":200.00
   }, ...
]
```

##Get Role

* `GET /roles/{roleId}` Returns a specific role.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the role|
|id | Integer|
|name | String|
|description | String|
|internalCostPrice | Decimal|
|externalCostPrice | Decimal|

###Sample JSON Response
```json
{
   "url":"https://api.forecast.it/api/v1/roles/1",
   "id":1,
   "name":"Developer",
   "description":"Developer resources",
   "internalCostPrice":110.00,
   "externalCostPrice":200.00
}
```

##Create Role

* `POST /roles` Creates a new role.

|Response Fields | Description/Format|
|------------ | -------------|
|name | (Required) String|
|description | (Optional) String|
|internalCostPrice | (Required) Decimal|
|externalCostPrice | (Required) Decimal|

###Sample JSON Request
POST https://api.forecast.it/api/v1/roles

```json
{
   "name":"Developer",
   "description":"Developer resources",
   "internalCostPrice":110.00,
   "externalCostPrice":200.00
}
```

##Update Role

* `PUT /roles/{roleId}` Update a role.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String|
|description | String|
|internalCostPrice | Decimal|
|externalCostPrice | Decimal|


###Sample JSON Request
PUT https://api.forecast.it/api/v1/roles/1

```json
{
   "name":"New Name",
   "internalCostPrice":42.00
}
```

##Delete Role

* `DELETE /roles/{roleId}` Deletes a role.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/roles/1
