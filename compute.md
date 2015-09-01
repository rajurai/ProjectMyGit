## *<font color='red'>Alliance Compute API v1 (CURRENT)</font>*
      
      This page lists the Compute API operations in the following order: 
      1. Servers
      2. Flavors
      
      
###  1. Servers
      
      Manages the server creation, updation, listing,Create the servers,Get the servres details,Upadate the servers,Delete the servers.

        Creates servers with the given information. The request and response examples show how to create multiple servers with or without a reservation ID

  <p>
  Servers information.
  </p>


METHOD  |  URI                                        |DESCRIPTION
--------|---------------------------------------------|-------------
GET     | /servers                                    |List servers
GET     | /servers/id                                 |Get specific server
POST    | /servers                                    |Create server
PATCH   | /servers/name                               |Update server
DELETE  | /servers/name                               |Delete servers



#### 1.1 List servers

METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
GET     | /servers                    |List servers

<p>
It shows list of servers present in database.
</p>

<p><b>Normal response codes</b>: 200
</p>
<p><b>Error response codes</b>: 
</p>
     
##### 1.1.1. List servers Request:

This operation does not accept a request body.

##### 1.1.2 List servers Response

###### Example 1. List servers : JSON response

```


```

#### 1.2  Get Specific server


METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
GET     | /servers/id                 |Get specific server

<p>
It shows specific server information whose id we passed in URI.
</p>

<p><b>Normal response codes</b>: 200 
</p>
<p><b>Error response codes</b>: 
</p>

     
##### 1.2.1. Get specific servers Request:

This operation does not accept a request body.


##### 1.2.2 Get specific server Response

###### Example 2. Get specific server : JSON response

```


```

#### 1.3  Create server

METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
POST    | /servers                    |Create server

<p>
It creates the server with its details that we send in request body in database.
</p>

##### Important 

<p>
For sending request through request body select raw as a body editor.
</p>

<p><b>Normal response codes</b>:200 
</p>
<p><b>Error response codes</b>: 
</p>

     
##### 1.3.1. Create server Request


###### Example 3. Create server : JSON request

```
{
    "server": {
        "name": "demo_instance_final",
        "flavor": "m1.small",
        "image": "cirros-0.3.4-x86_64-uec",
        "keyname": "admin-key",
        "network": "private"
    }
} 

```


##### 1.3.2 Create server Response

###### Example 4. Create server : JSON response

```

```

#### 1.4  Update server

METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
PATCH   | /servers/name               |Update server

<p>
It updates the server with its details that we send in request body.
</p>

##### Important 

<p>
For sending request through request body select raw as a body editor.
</p>

<p><b>Normal response codes</b>: 200
</p>
<p><b>Error response codes</b>: 
</p>

     
##### 1.4.1. Update server Request


###### Example 5. Update server : JSON request

```
{
    "server": {
        "new_name": "demo_instance_update"
    }
} 

```


##### 1.4.2 Update server Response

###### Example 6. Update server : JSON response

```


```

#### 1.5  Delete server


METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
DELETE  | /servers/name               |Delete servers

<p>
It delete the server information whose id we passed in URI.
</p>

<p><b>Normal response codes</b>: 
</p>
<p><b>Error response codes</b>: 
</p>

     
##### 1.5.1. Delete server Request:

This operation does not accept a request body.


##### 1.5.2 Delete server Response

This operation does not return any json response.



