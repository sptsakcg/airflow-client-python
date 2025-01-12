# Apache Airflow Python Client.PluginApi

All URIs are relative to *https://airflow.datalakefoundation.aws-dev.capgroup.com/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_plugins**](PluginApi.md#get_plugins) | **GET** /plugins | Get a list of loaded plugins


# **get_plugins**
> PluginCollection get_plugins()

Get a list of loaded plugins

### Example


```python
import time
import airflow_client.client
from airflow_client.client.api import plugin_api
from airflow_client.client.model.plugin_collection import PluginCollection
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
    api_instance = plugin_api.PluginApi(api_client)
    limit = 100 # int | The numbers of items to return. (optional) if omitted the server will use the default value of 100
    offset = 0 # int | The number of items to skip before starting to collect the result set. (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get a list of loaded plugins
        api_response = api_instance.get_plugins(limit=limit, offset=offset)
        pprint(api_response)
    except client.ApiException as e:
        print("Exception when calling PluginApi->get_plugins: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| The numbers of items to return. | [optional] if omitted the server will use the default value of 100
 **offset** | **int**| The number of items to skip before starting to collect the result set. | [optional]

### Return type

[**PluginCollection**](PluginCollection.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success |  -  |
**401** | Request not authenticated due to missing, invalid, authentication info. |  -  |
**403** | Client does not have sufficient permission. |  -  |
**404** | A specified resource is not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

