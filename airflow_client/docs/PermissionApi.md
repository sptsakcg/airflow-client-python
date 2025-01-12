# Apache Airflow Python Client.PermissionApi

All URIs are relative to *https://airflow.datalakefoundation.aws-dev.capgroup.com/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_permissions**](PermissionApi.md#get_permissions) | **GET** /permissions | List permissions


# **get_permissions**
> ActionCollection get_permissions()

List permissions

### Example


```python
import time
import airflow_client.client
from airflow_client.client.api import permission_api
from airflow_client.client.model.action_collection import ActionCollection
from airflow_client.client.model.error import Error
from pprint import pprint
# Defining the host is optional and defaults to https://airflow.datalakefoundation.aws-dev.capgroup.com/api/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = client.Configuration(
    host = "https://airflow.datalakefoundation.aws-dev.capgroup.com/api/v1"
)


# Enter a context with an instance of the API client
with client.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = permission_api.PermissionApi(api_client)
    limit = 100 # int | The numbers of items to return. (optional) if omitted the server will use the default value of 100
    offset = 0 # int | The number of items to skip before starting to collect the result set. (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # List permissions
        api_response = api_instance.get_permissions(limit=limit, offset=offset)
        pprint(api_response)
    except client.ApiException as e:
        print("Exception when calling PermissionApi->get_permissions: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| The numbers of items to return. | [optional] if omitted the server will use the default value of 100
 **offset** | **int**| The number of items to skip before starting to collect the result set. | [optional]

### Return type

[**ActionCollection**](ActionCollection.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success. |  -  |
**401** | Request not authenticated due to missing, invalid, authentication info. |  -  |
**403** | Client does not have sufficient permission. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

