# PetApi

All URIs are relative to *http://petstore.swagger.io/v2*

Method | HTTP request | Description
------------- | ------------- | -------------
[**AddPet**](PetApi.md#AddPet) | **POST** /pet | Add a new pet to the store
[**DeletePet**](PetApi.md#DeletePet) | **DELETE** /pet/{petId} | Deletes a pet
[**FindPetsByStatus**](PetApi.md#FindPetsByStatus) | **GET** /pet/findByStatus | Finds Pets by status
[**FindPetsByTags**](PetApi.md#FindPetsByTags) | **GET** /pet/findByTags | Finds Pets by tags
[**GetPetById**](PetApi.md#GetPetById) | **GET** /pet/{petId} | Find pet by ID
[**UpdatePet**](PetApi.md#UpdatePet) | **PUT** /pet | Update an existing pet
[**UpdatePetWithForm**](PetApi.md#UpdatePetWithForm) | **POST** /pet/{petId} | Updates a pet in the store with form data
[**UploadFile**](PetApi.md#UploadFile) | **POST** /pet/{petId}/uploadImage | uploads an image


# **AddPet**
> Pet AddPet(pet)

Add a new pet to the store



### Example
```R
library(petstore)

var_pet <- Pet$new("name_example", list("photoUrls_example"), 123, Category$new(123, "name_example"), list(Tag$new(123, "name_example")), "available") # Pet | Pet object that needs to be added to the store

#Add a new pet to the store
api_instance <- PetApi$new()
# Configure OAuth2 access token for authorization: petstore_auth
api_instance$api_client$access_token <- 'TODO_YOUR_ACCESS_TOKEN';
result <- tryCatch(
             # to save the result into a file, simply add the optional `data_file` parameter, e.g.
             # api_instance$AddPet(var_pet, data_file = "result.txt"),
             api_instance$AddPet(var_pet),
             ApiException = function(ex) ex
          )
# In case of error, print the error object
if (!is.null(result$ApiException)) {
  cat(result$ApiException$toString())
} else {
  # deserialized response object
  response.object <- result$content
  # response headers
  response.headers <- result$response$headers
  # response status code
  response.status.code <- result$response$status_code
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pet** | [**Pet**](Pet.md)| Pet object that needs to be added to the store | 

### Return type

[**Pet**](Pet.md)

### Authorization

[petstore_auth](../README.md#petstore_auth)

### HTTP request headers

 - **Content-Type**: application/json, application/xml, multipart/related
 - **Accept**: application/xml, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **405** | Invalid input |  -  |

# **DeletePet**
> DeletePet(pet_id, api_key = var.api_key)

Deletes a pet



### Example
```R
library(petstore)

var_pet_id <- 56 # integer | Pet id to delete
var_api_key <- 'api_key_example' # character | 

#Deletes a pet
api_instance <- PetApi$new()
# Configure OAuth2 access token for authorization: petstore_auth
api_instance$api_client$access_token <- 'TODO_YOUR_ACCESS_TOKEN';
result <- tryCatch(
             api_instance$DeletePet(var_pet_id, api_key = var_api_key),
             ApiException = function(ex) ex
          )
# In case of error, print the error object
if (!is.null(result$ApiException)) {
  cat(result$ApiException$toString())
} else {
  # response headers
  response.headers <- result$response$headers
  # response status code
  response.status.code <- result$response$status_code
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pet_id** | **integer**| Pet id to delete | 
 **api_key** | **character**|  | [optional] 

### Return type

void (empty response body)

### Authorization

[petstore_auth](../README.md#petstore_auth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Invalid pet value |  -  |

# **FindPetsByStatus**
> array[Pet] FindPetsByStatus(status)

Finds Pets by status

Multiple status values can be provided with comma separated strings

### Example
```R
library(petstore)

var_status <- list("available") # array[character] | Status values that need to be considered for filter

#Finds Pets by status
api_instance <- PetApi$new()
# Configure OAuth2 access token for authorization: petstore_auth
api_instance$api_client$access_token <- 'TODO_YOUR_ACCESS_TOKEN';
result <- tryCatch(
             # to save the result into a file, simply add the optional `data_file` parameter, e.g.
             # api_instance$FindPetsByStatus(var_status, data_file = "result.txt"),
             api_instance$FindPetsByStatus(var_status),
             ApiException = function(ex) ex
          )
# In case of error, print the error object
if (!is.null(result$ApiException)) {
  cat(result$ApiException$toString())
} else {
  # deserialized response object
  response.object <- result$content
  # response headers
  response.headers <- result$response$headers
  # response status code
  response.status.code <- result$response$status_code
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **status** | Enum [available, pending, sold] | Status values that need to be considered for filter | 

### Return type

[**array[Pet]**](Pet.md)

### Authorization

[petstore_auth](../README.md#petstore_auth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/xml, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid status value |  -  |

# **FindPetsByTags**
> array[Pet] FindPetsByTags(tags)

Finds Pets by tags

Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

### Example
```R
library(petstore)

var_tags <- list("inner_example") # array[character] | Tags to filter by

#Finds Pets by tags
api_instance <- PetApi$new()
# Configure OAuth2 access token for authorization: petstore_auth
api_instance$api_client$access_token <- 'TODO_YOUR_ACCESS_TOKEN';
result <- tryCatch(
             # to save the result into a file, simply add the optional `data_file` parameter, e.g.
             # api_instance$FindPetsByTags(var_tags, data_file = "result.txt"),
             api_instance$FindPetsByTags(var_tags),
             ApiException = function(ex) ex
          )
# In case of error, print the error object
if (!is.null(result$ApiException)) {
  cat(result$ApiException$toString())
} else {
  # deserialized response object
  response.object <- result$content
  # response headers
  response.headers <- result$response$headers
  # response status code
  response.status.code <- result$response$status_code
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **tags** | list( **character** )| Tags to filter by | 

### Return type

[**array[Pet]**](Pet.md)

### Authorization

[petstore_auth](../README.md#petstore_auth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/xml, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid tag value |  -  |

# **GetPetById**
> Pet GetPetById(pet_id)

Find pet by ID

Returns a single pet

### Example
```R
library(petstore)

var_pet_id <- 56 # integer | ID of pet to return

#Find pet by ID
api_instance <- PetApi$new()
# Configure API key authorization: api_key
api_instance$api_client$api_keys['api_key'] <- 'TODO_YOUR_API_KEY';
result <- tryCatch(
             # to save the result into a file, simply add the optional `data_file` parameter, e.g.
             # api_instance$GetPetById(var_pet_id, data_file = "result.txt"),
             api_instance$GetPetById(var_pet_id),
             ApiException = function(ex) ex
          )
# In case of error, print the error object
if (!is.null(result$ApiException)) {
  cat(result$ApiException$toString())
} else {
  # deserialized response object
  response.object <- result$content
  # response headers
  response.headers <- result$response$headers
  # response status code
  response.status.code <- result$response$status_code
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pet_id** | **integer**| ID of pet to return | 

### Return type

[**Pet**](Pet.md)

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/xml, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |

# **UpdatePet**
> Pet UpdatePet(pet)

Update an existing pet



### Example
```R
library(petstore)

var_pet <- Pet$new("name_example", list("photoUrls_example"), 123, Category$new(123, "name_example"), list(Tag$new(123, "name_example")), "available") # Pet | Pet object that needs to be added to the store

#Update an existing pet
api_instance <- PetApi$new()
# Configure OAuth2 access token for authorization: petstore_auth
api_instance$api_client$access_token <- 'TODO_YOUR_ACCESS_TOKEN';
result <- tryCatch(
             # to save the result into a file, simply add the optional `data_file` parameter, e.g.
             # api_instance$UpdatePet(var_pet, data_file = "result.txt"),
             api_instance$UpdatePet(var_pet),
             ApiException = function(ex) ex
          )
# In case of error, print the error object
if (!is.null(result$ApiException)) {
  cat(result$ApiException$toString())
} else {
  # deserialized response object
  response.object <- result$content
  # response headers
  response.headers <- result$response$headers
  # response status code
  response.status.code <- result$response$status_code
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pet** | [**Pet**](Pet.md)| Pet object that needs to be added to the store | 

### Return type

[**Pet**](Pet.md)

### Authorization

[petstore_auth](../README.md#petstore_auth)

### HTTP request headers

 - **Content-Type**: application/json, application/xml, multipart/related
 - **Accept**: application/xml, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |
| **400** | Invalid ID supplied |  -  |
| **404** | Pet not found |  -  |
| **405** | Validation exception |  -  |

# **UpdatePetWithForm**
> UpdatePetWithForm(pet_id, name = var.name, status = var.status)

Updates a pet in the store with form data



### Example
```R
library(petstore)

var_pet_id <- 56 # integer | ID of pet that needs to be updated
var_name <- 'name_example' # character | Updated name of the pet
var_status <- 'status_example' # character | Updated status of the pet

#Updates a pet in the store with form data
api_instance <- PetApi$new()
# Configure OAuth2 access token for authorization: petstore_auth
api_instance$api_client$access_token <- 'TODO_YOUR_ACCESS_TOKEN';
result <- tryCatch(
             api_instance$UpdatePetWithForm(var_pet_id, name = var_name, status = var_status),
             ApiException = function(ex) ex
          )
# In case of error, print the error object
if (!is.null(result$ApiException)) {
  cat(result$ApiException$toString())
} else {
  # response headers
  response.headers <- result$response$headers
  # response status code
  response.status.code <- result$response$status_code
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pet_id** | **integer**| ID of pet that needs to be updated | 
 **name** | **character**| Updated name of the pet | [optional] 
 **status** | **character**| Updated status of the pet | [optional] 

### Return type

void (empty response body)

### Authorization

[petstore_auth](../README.md#petstore_auth)

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **405** | Invalid input |  -  |

# **UploadFile**
> ModelApiResponse UploadFile(pet_id, additional_metadata = var.additional_metadata, file = var.file)

uploads an image



### Example
```R
library(petstore)

var_pet_id <- 56 # integer | ID of pet to update
var_additional_metadata <- 'additional_metadata_example' # character | Additional data to pass to server
var_file <- File.new('/path/to/file') # data.frame | file to upload

#uploads an image
api_instance <- PetApi$new()
# Configure OAuth2 access token for authorization: petstore_auth
api_instance$api_client$access_token <- 'TODO_YOUR_ACCESS_TOKEN';
result <- tryCatch(
             # to save the result into a file, simply add the optional `data_file` parameter, e.g.
             # api_instance$UploadFile(var_pet_id, additional_metadata = var_additional_metadata, file = var_file, data_file = "result.txt"),
             api_instance$UploadFile(var_pet_id, additional_metadata = var_additional_metadata, file = var_file),
             ApiException = function(ex) ex
          )
# In case of error, print the error object
if (!is.null(result$ApiException)) {
  cat(result$ApiException$toString())
} else {
  # deserialized response object
  response.object <- result$content
  # response headers
  response.headers <- result$response$headers
  # response status code
  response.status.code <- result$response$status_code
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pet_id** | **integer**| ID of pet to update | 
 **additional_metadata** | **character**| Additional data to pass to server | [optional] 
 **file** | **data.frame**| file to upload | [optional] 

### Return type

[**ModelApiResponse**](ApiResponse.md)

### Authorization

[petstore_auth](../README.md#petstore_auth)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | successful operation |  -  |

