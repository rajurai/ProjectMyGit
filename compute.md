## *<font color='red'>Alliance Compute API v1 (CURRENT)</font>*
      
      This page lists the Compute API operations in the following order: 
            1. Servers
            
            2. Flavors
      
      
###  1. Servers
      
      <p>This serction includes details information all the server actions available.</p>

  <p>
  Servers information.
  </p>


METHOD  |  URI                                        |DESCRIPTION
--------|---------------------------------------------|-------------
GET     | /servers                                    |List all the servers
GET     | /servers/<server_id>                        |Get the specific server 
POST    | /servers                                    |Creates a new server
PATCH   | /servers/<server_name>                      |Updates a server name
DELETE  | /servers/<server_name>                      |Deletes a server



#### 1.1 List servers

METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
GET     | /servers                    |List all the servers

<p>
It will list all the available servers information.
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

#### 1.2  Get a specific server


METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
GET     | /servers/<server_id>        |Get a specific server

<p>
It will show a specific servers information matching with an server id we are passing in URI.
</p>

<p><b>Normal response codes</b>: 200 
</p>
<p><b>Error response codes</b>: 
</p>

     
##### 1.2.1. Get specific server Request:

This operation does not accept a request body.


##### 1.2.2 Get specific server Response

###### Example 2. Get specific server : JSON response

```


```

#### 1.3  Creates a server

METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
POST    | /servers                    |Create server

<p>
It creates a new server with the details that we pass in the request body.
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
        "name": "demo_instance",
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
PATCH   | /servers/<server_name>      |Update server

<p>
It updates the server name with new name that we pass in the request body.
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
DELETE  | /servers/<server_name>      |Delete servers

<p>
It deletes a server matching with the name we pass in URI.
</p>

<p><b>Normal response codes</b>: 
</p>
<p><b>Error response codes</b>: 
</p>

     
##### 1.5.1. Delete server Request:

This operation does not accept a request body.


##### 1.5.2 Delete server Response

This operation does not return any json response.



