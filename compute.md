## *<font color='red'>Alliance Compute API v1 (CURRENT)</font>*
      
      This page lists the Compute API operations in the following order: 
            1. Servers
            
            2. Flavors
      
      
###  1. Servers
      
      This section includes details information all the server actions available.

  <p>
  Servers information.
  </p>


METHOD  |  URI                                        |DESCRIPTION
--------|---------------------------------------------|-------------
GET     | /servers                                    |List all the servers
GET     | /servers/\<server_id>                       |Get the specific server 
POST    | /servers                                    |Creates a new server
PATCH   | /servers/\<server_name>                     |Updates a server name
DELETE  | /servers/\<server_name>                     |Deletes a server



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

GET http://\<servername>:\<port_no>/servers/

##### 1.1.2 List servers Response

###### Example 1. List servers : JSON response

```
{
  "servers": [
    {
      "id": "7dd1a243-8bc0-45a6-b63f-5155e0e3d8ec",
      "links": [
        {
          "href": "http://128.107.2.152:8774/v2/54915a05b0bb43dcbb218525c426b6a5/servers/7dd1a243-8bc0-45a6-b63f-5155e0e3d8ec",
          "rel": "self"
        },
        {
          "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/servers/7dd1a243-8bc0-45a6-b63f-5155e0e3d8ec",
          "rel": "bookmark"
        }
      ],
      "name": "ctlr-server"
    },
    {
      "id": "3a735203-a882-45a9-a604-342681166d5c",
      "links": [
        {
          "href": "http://128.107.2.152:8774/v2/54915a05b0bb43dcbb218525c426b6a5/servers/3a735203-a882-45a9-a604-342681166d5c",
          "rel": "self"
        },
        {
          "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/servers/3a735203-a882-45a9-a604-342681166d5c",
          "rel": "bookmark"
        }
      ],
      "name": "minecraft-server"
    }
  ]
}

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

GET http://\<servername>:\<port_no>/servers/\<server_id>


##### 1.2.2 Get specific server Response

###### Example 2. Get specific server : JSON response

```
{
  "server": {
    "status": "ACTIVE",
    "hostId": "39abeaf7293690a5ded13d38b4c475f901631a7beb78aff4d22607fd",
    "addresses": {
      "public": [
        {
          "OS-EXT-IPS-MAC:mac_addr": "fa:16:3e:1c:bb:cf",
          "version": 4,
          "addr": "192.168.20.5",
          "OS-EXT-IPS:type": "fixed"
        }
      ],
      "private": [
        {
          "OS-EXT-IPS-MAC:mac_addr": "fa:16:3e:1c:b2:a3",
          "version": 4,
          "addr": "192.168.15.4",
          "OS-EXT-IPS:type": "fixed"
        }
      ]
    },
    "links": [
      {
        "href": "http://128.107.2.152:8774/v2/54915a05b0bb43dcbb218525c426b6a5/servers/7dd1a243-8bc0-45a6-b63f-5155e0e3d8ec",
        "rel": "self"
      },
      {
        "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/servers/7dd1a243-8bc0-45a6-b63f-5155e0e3d8ec",
        "rel": "bookmark"
      }
    ],
    "image": {
      "id": "c48add99-3cd3-4d41-90ff-5ebed89395ac",
      "links": [
        {
          "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/images/c48add99-3cd3-4d41-90ff-5ebed89395ac",
          "rel": "bookmark"
        }
      ]
    },
    "flavor": {
      "id": "2",
      "links": [
        {
          "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/flavors/2",
          "rel": "bookmark"
        }
      ]
    },
    "networks": {
      "public": [
        "192.168.20.5"
      ],
      "private": [
        "192.168.15.4"
      ]
    },
    "name": "ctlr-server",
    "created": "2015-08-10T19:59:49Z",
    "tenant_id": "54915a05b0bb43dcbb218525c426b6a5",
    "id": "7dd1a243-8bc0-45a6-b63f-5155e0e3d8ec",
    "progress": 0
  }
}


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

POST http://\<servername>:\<port_no>/servers/

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
{
  "server": {
    "name": [
      {
        "href": "http://128.107.2.152:8774/v2/54915a05b0bb43dcbb218525c426b6a5/servers/827e0c8a-910d-46f4-9afd-380850949952",
        "rel": "self"
      },
      {
        "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/servers/827e0c8a-910d-46f4-9afd-380850949952",
        "rel": "bookmark"
      }
    ],
    "imageRef": {
      "id": "c48add99-3cd3-4d41-90ff-5ebed89395ac",
      "links": [
        {
          "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/images/c48add99-3cd3-4d41-90ff-5ebed89395ac",
          "rel": "bookmark"
        }
      ]
    },
    "flavorRef": {
      "id": "2",
      "links": [
        {
          "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/flavors/2",
          "rel": "bookmark"
        }
      ]
    },
    "id": "827e0c8a-910d-46f4-9afd-380850949952",
    "networks": {},
    "security_groups": [
      {
        "name": "default"
      }
    ],
    "metadata": {}
  }
}

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

PATCH http://\<servername>:\<port_no>/servers/\<server_name>

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
{
  "server": {
    "status": "ACTIVE",
    "hostId": "39abeaf7293690a5ded13d38b4c475f901631a7beb78aff4d22607fd",
    "addresses": {
      "public": [
        {
          "version": 4,
          "addr": "192.168.20.62"
        }
      ],
      "private": [
        {
          "version": 4,
          "addr": "192.168.15.55"
        }
      ]
    },
    "links": [
      {
        "href": "http://128.107.2.152:8774/v2/54915a05b0bb43dcbb218525c426b6a5/servers/827e0c8a-910d-46f4-9afd-380850949952",
        "rel": "self"
      },
      {
        "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/servers/827e0c8a-910d-46f4-9afd-380850949952",
        "rel": "bookmark"
      }
    ],
    "image": {
      "id": "c48add99-3cd3-4d41-90ff-5ebed89395ac",
      "links": [
        {
          "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/images/c48add99-3cd3-4d41-90ff-5ebed89395ac",
          "rel": "bookmark"
        }
      ]
    },
    "flavor": {
      "id": "2",
      "links": [
        {
          "href": "http://128.107.2.152:8774/54915a05b0bb43dcbb218525c426b6a5/flavors/2",
          "rel": "bookmark"
        }
      ]
    },
    "networks": {
      "public": [
        "192.168.20.62"
      ],
      "private": [
        "192.168.15.55"
      ]
    },
    "name": "code_instance_update",
    "created": "2015-09-02T04:31:37Z",
    "tenant_id": "54915a05b0bb43dcbb218525c426b6a5",
    "id": "827e0c8a-910d-46f4-9afd-380850949952",
    "progress": 0
  }
}

```

#### 1.5  Delete server


METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
DELETE  | /servers/\<server_name>      |Delete servers

<p>
It deletes a server matching with the name we pass in URI.
</p>

<p><b>Normal response codes</b>:200 OK 
</p>
<p><b>Error response codes</b>: 
</p>

     
##### 1.5.1. Delete server Request:

DELETE http://\<servername>:\<port_no>/servers/\<server_name>


##### 1.5.2 Delete server Response

This operation does not return any json response.


