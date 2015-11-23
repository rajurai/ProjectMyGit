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
[
  {
    images:
  {
    "status": "queued",
    "created_at": "2015-09-25T15:49:21Z",
    "name": "cirrosimage",
    "tags": [],
    "container_format": "bare",
    "min_ram": 0,
    "disk_format": "qcow2",
    "updated_at": "2015-09-25T15:49:21Z",
    "visibility": "private",
    "copy_from": "http://cloudhyd.com/openstack/images/cirros-0.3.0-i386-disk.img",
    "owner": "54915a05b0bb43dcbb218525c426b6a5",
    "schema": "/v2/schemas/image",
    "protected": false,
    "file": "/v2/images/75da8211-b8d3-4329-a12b-953e7db4690a/file",
    "checksum": null,
    "min_disk": 0,
    "virtual_size": null,
    "id": "75da8211-b8d3-4329-a12b-953e7db4690a",
    "size": null
  },
  {
    "status": "queued",
    "created_at": "2015-09-25T15:29:08Z",
    "name": "telstaimage",
    "tags": [],
    "container_format": "bare",
    "min_ram": 1,
    "disk_format": "qcow2",
    "updated_at": "2015-09-25T15:29:08Z",
    "visibility": "private",
    "copy_from": "http://cloudhyd.com/openstack/images/cirros-0.3.0-i386-disk.img",
    "owner": "54915a05b0bb43dcbb218525c426b6a5",
    "schema": "/v2/schemas/image",
    "protected": false,
    "file": "/v2/images/1e29aea2-cd8b-4a76-b829-3ae8be5bc1ad/file",
    "checksum": null,
    "min_disk": 500,
    "virtual_size": null,
    "id": "1e29aea2-cd8b-4a76-b829-3ae8be5bc1ad",
    "size": null
  }
}
]

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
    "created_at": "2015-07-22T05:27:55Z",
    "name": "cirros-0.3.2-x86_64-uec-ramdisk",
    "tags": [],
    "container_format": "ari",
    "min_ram": 0,
    "disk_format": "ari",
    "updated_at": "2015-07-22T05:27:55Z",
    "visibility": "public",
    "owner": "54915a05b0bb43dcbb218525c426b6a5",
    "schema": "/v2/schemas/image",
    "protected": false,
    "file": "/v2/images/9cd36ea3-f225-4383-ae0a-61a020112223/file",
    "checksum": "68085af2609d03e51c7662395b5b6e4b",
    "min_disk": 0,
    "virtual_size": null,
    "id": "9cd36ea3-f225-4383-ae0a-61a020112223",
    "size": 3723817
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
  "created_at": "2015-09-28T18:57:46Z",
  "name": "cirrosimage",
  "tags": [],
  "container_format": "bare",
  "min_ram": 500,
  "disk_format": "qcow2",
  "updated_at": "2015-09-28T18:57:46Z",
  "visibility": "private",
  "copy_from": "http://cloudhyd.com/openstack/images/cirros-0.3.0-i386-disk.img",
  "owner": "54915a05b0bb43dcbb218525c426b6a5",
  "schema": "/v2/schemas/image",
  "protected": false,
  "file": "/v2/images/1abcd75b-3385-43e6-94fb-948d1b241774/file",
  "checksum": null,
  "min_disk": 1,
  "virtual_size": null,
  "id": "1abcd75b-3385-43e6-94fb-948d1b241774",
  "size": null
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
  "created_at": "2015-09-28T18:57:46Z",
  "name": "ubuntu_image",
  "tags": [],
  "container_format": "bare",
  "min_ram": 500,
  "disk_format": "qcow2",
  "updated_at": "2015-09-28T18:57:46Z",
  "visibility": "private",
  "copy_from": "http://cloudhyd.com/openstack/images/cirros-0.3.0-i386-disk.img",
  "owner": "54915a05b0bb43dcbb218525c426b6a5",
  "schema": "/v2/schemas/image",
  "protected": false,
  "file": "/v2/images/1abcd75b-3385-43e6-94fb-948d1b241774/file",
  "checksum": null,
  "min_disk": 1,
  "virtual_size": null,
  "id": "1abcd75b-3385-43e6-94fb-948d1b241774",
  "size": null
}
```

#### 1.5  Delete image


METHOD  |  URI                        |DESCRIPTION
--------|---------------------------- |-------------
DELETE  | /images/\<image_id>      |Delete image

<p>
It deletes a image matching with the id we pass in URI.
</p>

<p><b>Normal response code</b>:200 OK 
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



