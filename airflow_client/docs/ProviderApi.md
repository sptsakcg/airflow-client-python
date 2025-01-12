# Apache Airflow Python Client.ProviderApi

All URIs are relative to *https://airflow.datalakefoundation.aws-dev.capgroup.com/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_providers**](ProviderApi.md#get_providers) | **GET** /providers | List providers


# **get_providers**
> bool, date, datetime, dict, float, int, list, str, none_type get_providers()

List providers

### Example


```python
import time
import airflow_client.client
from airflow_client.client.api import provider_api
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
    api_instance = provider_api.ProviderApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # List providers
        api_response = api_instance.get_providers()
        pprint(api_response)
    except client.ApiException as e:
        print("Exception when calling ProviderApi->get_providers: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

**bool, date, datetime, dict, float, int, list, str, none_type**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of providers. |  -  |
**401** | Request not authenticated due to missing, invalid, authentication info. |  -  |
**403** | Client does not have sufficient permission. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

