## *<font color='red'>Alliance Glance API v1 (CURRENT)</font>*
      
      This page lists the images API operations available: 
            1. Image
            
      
###  1. Image
      
      This section includes the detailed information of all the image actions available.

  <p>
  Image information.
  </p>


METHOD  |  URI                                        |DESCRIPTION
--------|---------------------------------------------|-------------
GET     | /images                                     |List all the images
GET     | /images/\<image_id>                         |Get the specific image 
POST    | /images                                     |Creates a new image
PATCH   | /images/\<image_id>                         |Updates an image information
DELETE  | /images/\<image_id>                         |Deletes an image



#### 1.1 List images

METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
GET     | /images                     |List all the images

<p>
It will list all the available images information.
</p>

<p><b>Normal response code</b>: 200
</p>

##### 1.1.1. List images Request:

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for List images Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
Content-Type          | String                      | application/json
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5


GET http://\<hostname>:\<port_no>/images/

##### 1.1.2 List images Response

###### Example 1. List images : JSON response

```
{
  "image": [
    {
      "status": "active",
      "_loaded": true,
      "name": "cirros-0.3.4-x86_64-uec",
      "deleted": false,
      "container_format": "ami",
      "created_at": "2015-12-02T11:05:53.000000",
      "disk_format": "ami",
      "updated_at": "2015-12-02T11:05:54.000000",
      "id": "dc00e717-12a4-4570-8c60-ed47be0c34f8",
      "min_disk": 0,
      "protected": false,
      "min_ram": 0,
      "checksum": "eb9139e4942121f22bbc2afc0400b2a4",
      "owner": "c4a203c39b8e4ecb91feff1a9820dca8",
      "is_public": true,
      "virtual_size": null,
      "properties": {
        "kernel_id": "74f8e168-a2ba-486d-ae87-ef2aa7b482d2",
        "ramdisk_id": "57ed5365-e4a6-466e-9250-c427ecf0e465"
      },
      "size": 25165824
    },
    {
      "status": "active",
      "_loaded": true,
      "name": "cirros-0.3.4-x86_64-uec-ramdisk",
      "deleted": false,
      "container_format": "ari",
      "created_at": "2015-12-02T11:05:51.000000",
      "disk_format": "ari",
      "updated_at": "2015-12-02T11:05:52.000000",
      "id": "57ed5365-e4a6-466e-9250-c427ecf0e465",
      "min_disk": 0,
      "protected": false,
      "min_ram": 0,
      "checksum": "be575a2b939972276ef675752936977f",
      "owner": "c4a203c39b8e4ecb91feff1a9820dca8",
      "is_public": true,
      "virtual_size": null,
      "properties": {},
      "size": 3740163
    }
  ]
}
```

#### 1.2  Get a specific image


METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
GET     | /images/\<image_id>        |Get a specific image

<p>
It will show a specific image information matching with an image id we are passing in URI.
</p>

<p><b>Normal response code</b>: 200 
</p>

     
##### 1.2.1. Get specific image Request:

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for Get specific image Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
Content-Type          | String                      | application/json
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5


GET http://\<hostname>:\<port_no>/images/\<image_id>


##### 1.2.2 Get specific image Response

###### Example 2. Get specific image : JSON response

```
{
  "status": "active",
  "name": "cirros-0.3.4-x86_64-uec-ramdisk",
  "deleted": false,
  "container_format": "ari",
  "created_at": "2015-12-02T11:05:51.000000",
  "disk_format": "ari",
  "updated_at": "2015-12-02T11:05:52.000000",
  "id": "57ed5365-e4a6-466e-9250-c427ecf0e465",
  "min_disk": 0,
  "protected": false,
  "checksum": "be575a2b939972276ef675752936977f",
  "owner": "c4a203c39b8e4ecb91feff1a9820dca8",
  "is_public": true,
  "_loaded": false,
  "min_ram": 0,
  "size": 3740163
}

```

#### 1.3  Creates a image

METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
POST    | /images                    |Create image

<p>
It creates a new image with the details that we pass in the request body.
</p>

##### Important 

<p>
For sending request through request body select raw as a body editor.
</p>

<p><b>Normal response code</b>:201
</p>

     
##### 1.3.1. Create image Request

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for Create image Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
Content-Type          | String                      | application/json
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5

POST http://\<hostname>:\<port_no>/images/

###### Example 3. Create image : JSON request

```
{
    "image":
    {
        "name": "remote_image",
        "disk_format": "qcow2",
        "container_format": "bare",
        "copy_from":"http://cloudhyd.com/openstack/images/cirros-0.3.0-i386-disk.img",
        "min_ram":1,
        "min_disk":500
    }
}
```


##### 1.3.2 Create image Response

###### Example 4. Create image : JSON response

```
{
  "status": "queued",
  "name": "glance_image_remote",
  "deleted": false,
  "container_format": "bare",
  "created_at": "2015-12-16T05:41:32.000000",
  "disk_format": "iso",
  "updated_at": "2015-12-16T05:41:32.000000",
  "id": "c4aef384-ca6b-4215-987c-00cc864b625e",
  "min_disk": 500,
  "protected": false,
  "checksum": null,
  "owner": "85ee3d12cb6947d5b4bb479c8944d4dc",
  "is_public": false,
  "_loaded": false,
  "min_ram": 1,
  "size": 1054867456
}

```

#### 1.4  Update image

METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
PATCH   | /images/\<image_id>      |Update image

<p>
It updates the image name with new name that we pass in the request body.
</p>

##### Important 

<p>
For sending request through request body select raw as a body editor.
</p>

<p><b>Normal response code</b>: 200
</p>

     
##### 1.4.1. Update image Request

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for Update image Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
Content-Type          | String                      | application/json
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5

PUT http://\<hostname>:\<port_no>/images/\<image_name>

###### Example 5. Update image : JSON request

```
{
    "image": {
        "name": "ubuntu_image",
        "disk_format": "ari",
        "container_format": "bare",
        "min_ram":1,
        "min_disk":500
       
    }
}

```


##### 1.4.2 Update image Response

###### Example 6. Update image : JSON response

```
{
  "status": "queued",
  "name": "ubuntu_image",
  "deleted": false,
  "container_format": "bare",
  "created_at": "2015-12-16T05:41:32.000000",
  "disk_format": "ari",
  "updated_at": "2015-12-16T05:43:19.000000",
  "id": "c4aef384-ca6b-4215-987c-00cc864b625e",
  "min_disk": 500,
  "protected": false,
  "checksum": null,
  "owner": "85ee3d12cb6947d5b4bb479c8944d4dc",
  "is_public": false,
  "_loaded": false,
  "min_ram": 1,
  "size": 1054867456
}

```

#### 1.5  Delete image


METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
DELETE  | /images/\<image_id>      |Delete image

<p>
It deletes a image matching with the id we pass in URI.
</p>

<p><b>Normal response code</b>:204  
</p>

     
##### 1.5.1. Delete image Request:

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This table shows the header parameters for Delete image Request:</p>

Name                  |  Type                       |Value
----------------------|---------------------------- |-------------
Content-Type          | String                      | application/json
X-Target-Ns           | String                      |\<namespace>eg.ccsr1
X-Environment-Id      | String                      |\<environment-id>eg.54915a05b0bb43dcbb218525c426b6a5

DELETE http://\<hostname>:\<port_no>/images/\<image_id>


##### 1.5.2 Delete image Response

This operation does not return any json response.


