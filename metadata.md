
## *<font color='red'>Alliance Metadata API v1 (CURRENT)</font>*

    This page lists the Metadata operations for a partner: 

###  1. Metadata

           Metadata information.

METHOD  |  URI                                               |DESCRIPTION
--------|----------------------------------------------------|-------------
GET     | /partners/\<partner_id>/metadata/                  |List all metadata's of a partner
GET     | /partners/\<partner_id>/metadata/\<metadata_id>    |Get specific metadata of a partner
POST    | /partners/\<partner_id>/metadata/                  |Add Metadata for specific partner
PATCH   | /partners/\<partner_id>/metadata/\<metadata_id>    |Update specific metadata of partner 
DELETE  | /partners/\<partner_id>/metadata/\<metadata_id>    |Delete specific metadata of partner

#### 1.1 List all metadata's of partner

METHOD  |  URI                                 |DESCRIPTION
--------|--------------------------------------|-------------
GET     | /partners/\<partner_id>/metadata/    |List all metadata's of a partner

It shows all metadata's of a partner present in database.

**Normal response codes**: 200

**Error response codes**: 
    
##### 1.1.1. List all metadata's of partner:

This operation does not accept a request body.

##### 1.1.2 List all metadata's of partner Response

###### Example 1. List all metadata's of partner : JSON response

```
{
  "total": 2,
  "metadeta": [
    {
      "status": "ACTIVE",
      "updated": "2015-11-10T06:36:07.980421",
      "created": "2015-11-10T06:36:07.980390",
      "namespace": "ctlr2",
      "type": "public_key",
      "id": "fdfdb9dc-9361-498c-8f97-fa7a437b70a8",
      "value": "public_key_value"
    },
    {
      "status": "ACTIVE",
      "updated": "2015-11-10T06:38:53.514034",
      "created": "2015-11-10T06:38:53.514001",
      "namespace": "ctlr2",
      "type": "endpoint",
      "id": "9fb4af0e-37d6-4be8-9297-6a38ca9c2b13",
      "value": "192.168.56.102:9441"
    }
  ]
}

```

#### 1.2 Get specific metadata of a partner

METHOD  |  URI                                               |DESCRIPTION
--------|----------------------------------------------------|-------------
GET     | /partners/\<partner_id>/metadata/\<metadata_id>    |Get specific metadata of a partner

It shows specific metadata of a partner whose metadata_id we passed in URI.

**Normal response codes**: 200

**Error response codes**: 
    
##### 1.2.1. Get specific metadata of a partner Request :

This operation does not accept a request body.

##### 1.2.2 Get specific metadata of a partner Response :

###### Example 2. Get specific metadata of a partner : JSON response

```
{
  "status": "ACTIVE",
  "updated": "2015-11-10T06:36:07.980421",
  "created": "2015-11-10T06:36:07.980390",
  "namespace": "ctlr2",
  "type": "public_key",
  "id": "fdfdb9dc-9361-498c-8f97-fa7a437b70a8",
  "value": "public_key_value"
}

```

#### 1.3  Add Metadata for a specific partner

METHOD  |  URI                               |DESCRIPTION
--------|----------------------------------- |-------------
POST    | /partners/\<partner_id>/metadata/  |Add Metadata for a specific partner


It adds Metadata for a specific partner with its details that we send in request body through postman.

##### Important 

For sending request through request body select raw as a body editor.

**Normal response codes**: 201 

**Error response codes**: 

##### 1.3.1. Add Metadata Request

###### Example 3. Add public key metadata : JSON request

```
{
    "type": "public_key",
    "value":"public_key_value"
}


```

##### 1.3.2 Add Metadata Response

###### Example 4. Add public key metadata : JSON response

```
{
  "metadata": {
    "status": "ACTIVE",
    "created": "2015-11-10 06:36:07.980390",
    "namespace": "ctlr2",
    "value": "public_key_value",
    "type": "public_key",
    "id": "fdfdb9dc-9361-498c-8f97-fa7a437b70a8"
  }
}

```

##### 1.3.3 Add Metadata Request

###### Example 5. Add endpoint metadata : JSON request

```
{
    "type": "endpoint",
    "value":"<host>:<port>" (ex:192.168.56.102:9441)
}

```

##### 1.3.4 Add Metadata Response

###### Example 6. Add endpoint metadata : JSON response

```
{
  "metadata": {
    "status": "ACTIVE",
    "created": "2015-11-10 05:39:27.408389",
    "namespace": "ctlr2",
    "value": "192.168.56.102:9441",
    "type": "endpoint",
    "id": "8ef54694-fc3e-4c34-b63f-0cd6215df0dd"
  }
}

```



#### 1.4  Update Metadata 

METHOD  |  URI                                               |DESCRIPTION
--------|--------------------------------------------------- |-------------
PATCH   | /partners/\<partner_id>/metadata/\<metadata_id>    |Update specific metadata of partner

It updates the specific metadata of partner with its details whose metadata_id we passed in URI.

##### Important 

For sending request through request body select raw as a body editor.

**Normal response codes**: 200

**Error response codes**: 
 
##### 1.4.1. Update Metadata Request

###### Example 7. Update Metadata : JSON request

```
{
    "type": "public_key",
    "value":"public_key_value_updated"
}

```

##### 1.4.2 Update Metadata Response

###### Example 8. Update Metadata : JSON response

```
{
  "metadata": {
    "status": "ACTIVE",
    "created": "2015-11-10 06:36:07.980390",
    "namespace": "ctlr2",
    "value": "public_key_value_updated",
    "type": "public_key",
    "id": "fdfdb9dc-9361-498c-8f97-fa7a437b70a8"
  }
}
```


#### 1.5  Delete Metadata 


METHOD  |  URI                                               |DESCRIPTION
--------|----------------------------------------------------|-------------
DELETE  |  /partners/\<partner_id>/metadata/\<metadata_id>   |Delete specific metadata of partner 

It delete the specific metadata of a partner whose metadata_id we passed in URI.

**Normal response codes**:204 

**Error response codes**: 
 
##### 1.5.1. Delete Metadata Request:

This operation does not accept a request body.


##### 1.5.2 Delete Metadata Response

This operation does not return any json response.


