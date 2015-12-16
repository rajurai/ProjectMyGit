## *<font color='red'>Alliance Compute API v1 (CURRENT)</font>*
      
      This page lists the Compute API operations available: 
            1. Servers
            
      
###  1. Servers
      
      This section includes the detailed information of all the server actions available.

  <p>
  Servers information.
  </p>


METHOD  |  URI                                        |DESCRIPTION
--------|---------------------------------------------|-------------
GET     | /servers                                    |List all the servers
GET     | /servers/\<server_id>                       |Get the specific server 
POST    | /servers                                    |Creates a new server
PATCH   | /servers/\<server_id>                       |Updates a server name
DELETE  | /servers/\<server_id>                       |Deletes a server



#### 1.1 List servers

METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
GET     | /servers                    |List all the servers

<p>
It will list all the available servers information.
</p>

<p><b>Normal response code</b>: 200
</p>
<p><b>Error response code</b>: 
</p>
     
##### 1.1.1. List servers Request:

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for List servers Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5


GET http://\<servername>:\<port_no>/servers/

##### 1.1.2 List servers Response

###### Example 1. List servers : JSON response

```
{
  "servers": [
    {
      "OS-EXT-STS:task_state": null,
      "addresses": {
        "demo_network_1": [
          {
            "OS-EXT-IPS-MAC:mac_addr": "fa:16:3e:c6:ad:77",
            "version": 4,
            "addr": "192.168.10.2",
            "OS-EXT-IPS:type": "fixed"
          }
        ],
        "demo_network_2": [
          {
            "OS-EXT-IPS-MAC:mac_addr": "fa:16:3e:68:4a:ff",
            "version": 4,
            "addr": "192.168.11.2",
            "OS-EXT-IPS:type": "fixed"
          }
        ]
      },
      "links": [
        {
          "href": "http://128.107.32.235:8774/v2/85ee3d12cb6947d5b4bb479c8944d4dc/servers/0029efd3-fc5a-4a78-b0d4-a42f01a6cec3",
          "rel": "self"
        },
        {
          "href": "http://128.107.32.235:8774/85ee3d12cb6947d5b4bb479c8944d4dc/servers/0029efd3-fc5a-4a78-b0d4-a42f01a6cec3",
          "rel": "bookmark"
        }
      ],
      "image": {
        "id": "dc00e717-12a4-4570-8c60-ed47be0c34f8",
        "links": [
          {
            "href": "http://128.107.32.235:8774/85ee3d12cb6947d5b4bb479c8944d4dc/images/dc00e717-12a4-4570-8c60-ed47be0c34f8",
            "rel": "bookmark"
          }
        ]
      },
      "OS-EXT-STS:vm_state": "active",
      "OS-SRV-USG:launched_at": "2015-12-15T07:30:12.000000",
      "flavor": {
        "id": "1",
        "links": [
          {
            "href": "http://128.107.32.235:8774/85ee3d12cb6947d5b4bb479c8944d4dc/flavors/1",
            "rel": "bookmark"
          }
        ]
      },
      "id": "0029efd3-fc5a-4a78-b0d4-a42f01a6cec3",
      "security_groups": [
        {
          "name": "default"
        },
        {
          "name": "default"
        }
      ],
      "user_id": "2b2b17dfcae14e5893e7a7cc0d553820",
      "OS-DCF:diskConfig": "MANUAL",
      "accessIPv4": "",
      "accessIPv6": "",
      "progress": 0,
      "OS-EXT-STS:power_state": 1,
      "OS-EXT-AZ:availability_zone": "nova",
      "config_drive": "True",
      "status": "ACTIVE",
      "updated": "2015-12-15T07:30:12Z",
      "hostId": "3dec2d4cb66703af03f92719027440b967555c8840ee71587b892195",
      "OS-SRV-USG:terminated_at": null,
      "key_name": "nova_keypair",
      "name": "nova_instance",
      "created": "2015-12-15T07:30:07Z",
      "tenant_id": "85ee3d12cb6947d5b4bb479c8944d4dc",
      "os-extended-volumes:volumes_attached": [],
      "metadata": {}
    }
  ]
}

```

#### 1.2  Get a specific server


METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
GET     | /servers/\<server_id>       |Get a specific server

<p>
It will show a specific servers information matching with an server id we are passing in URI.
</p>

<p><b>Normal response code</b>: 200 
</p>
<p><b>Error response code</b>: 
</p>

     
##### 1.2.1. Get specific server Request:

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for Get specific server Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5

GET http://\<servername>:\<port_no>/servers/\<server_id>


##### 1.2.2 Get specific server Response

###### Example 2. Get specific server : JSON response

```
{
  "server": {
    "OS-EXT-STS:task_state": null,
    "addresses": {
      "ctlr3_network": [
        {
          "OS-EXT-IPS-MAC:mac_addr": "fa:16:3e:09:0e:ca",
          "version": 4,
          "addr": "192.168.20.7",
          "OS-EXT-IPS:type": "fixed"
        }
      ]
    },
    "links": [
      {
        "href": "http://128.107.32.235:8774/v2/85ee3d12cb6947d5b4bb479c8944d4dc/servers/e0e260a9-9af0-46d1-ae61-1e0cee2cc66e",
        "rel": "self"
      },
      {
        "href": "http://128.107.32.235:8774/85ee3d12cb6947d5b4bb479c8944d4dc/servers/e0e260a9-9af0-46d1-ae61-1e0cee2cc66e",
        "rel": "bookmark"
      }
    ],
    "image": {
      "id": "dc00e717-12a4-4570-8c60-ed47be0c34f8",
      "links": [
        {
          "href": "http://128.107.32.235:8774/85ee3d12cb6947d5b4bb479c8944d4dc/images/dc00e717-12a4-4570-8c60-ed47be0c34f8",
          "rel": "bookmark"
        }
      ]
    },
    "OS-EXT-STS:vm_state": "active",
    "OS-SRV-USG:launched_at": "2015-12-11T09:22:08.000000",
    "flavor": {
      "id": "1",
      "links": [
        {
          "href": "http://128.107.32.235:8774/85ee3d12cb6947d5b4bb479c8944d4dc/flavors/1",
          "rel": "bookmark"
        }
      ]
    },
    "id": "e0e260a9-9af0-46d1-ae61-1e0cee2cc66e",
    "security_groups": [
      {
        "name": "default"
      }
    ],
    "user_id": "2b2b17dfcae14e5893e7a7cc0d553820",
    "OS-DCF:diskConfig": "MANUAL",
    "accessIPv4": "",
    "accessIPv6": "",
    "progress": 0,
    "OS-EXT-STS:power_state": 1,
    "OS-EXT-AZ:availability_zone": "nova",
    "config_drive": "True",
    "status": "ACTIVE",
    "updated": "2015-12-11T09:22:10Z",
    "hostId": "3dec2d4cb66703af03f92719027440b967555c8840ee71587b892195",
    "OS-SRV-USG:terminated_at": null,
    "key_name": "nova_keypair",
    "name": "test_hori_1",
    "created": "2015-12-11T09:22:02Z",
    "tenant_id": "85ee3d12cb6947d5b4bb479c8944d4dc",
    "os-extended-volumes:volumes_attached": [],
    "metadata": {}
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

<p><b>Normal response code</b>:201
</p>
<p><b>Error response code</b>: 
</p>

     
##### 1.3.1. Create server Request

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for Create server Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5


POST http://\<servername>:\<port_no>/servers/

###### Example 3. Create server : JSON request

```
{
    "server": {
        "name": "demo_instance",
        "flavor": "42",
        "image": "c9dcc32d-60f1-4e17-8996-046216fe9746",
        "keyname": "nova_keypair",
        "security_groups": "",
        "min_count":"1",
        "networks": "[{'net-id':'fc6b502a-5365-4c24-93e5-e40bfdf7c5a0', 'v4-fixed-ip': ''}]"
    }  
}
```


##### 1.3.2 Create server Response

###### Example 4. Create server : JSON response

```
{
  "server": {
    "name": "demo_instance" [
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
PATCH   | /servers/\<server_id>       |Update server

<p>
It updates the server name with new name that we pass in the request body.
</p>

##### Important 

<p>
For sending request through request body select raw as a body editor.
</p>

<p><b>Normal response code</b>: 200
</p>
<p><b>Error response code</b>: 
</p>

     
##### 1.4.1. Update server Request

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for Update server Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5

PATCH http://\<servername>:\<port_no>/servers/\<server_id>

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
    "name": "demo_instance_update",
    "created": "2015-09-02T04:31:37Z",
    "tenant_id": "54915a05b0bb43dcbb218525c426b6a5",
    "id": "827e0c8a-910d-46f4-9afd-380850949952",
 }
}

```

#### 1.5  Delete server


METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
DELETE  | /servers/\<server_id>       |Delete servers

<p>
It deletes a server matching with the name we pass in URI.
</p>

<p><b>Normal response code</b>:204 
</p>
<p><b>Error response code</b>: 
</p>

     
##### 1.5.1. Delete server Request:

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for Delete server Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5

DELETE http://\<servername>:\<port_no>/servers/\<server_id>


##### 1.5.2 Delete server Response

This operation does not return any json response.

