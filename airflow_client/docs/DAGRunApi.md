# Apache Airflow Python Client.DAGRunApi

All URIs are relative to *https://airflow.datalakefoundation.aws-dev.capgroup.com/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_dag_run**](DAGRunApi.md#delete_dag_run) | **DELETE** /dags/{dag_id}/dagRuns/{dag_run_id} | Delete a DAG run
[**get_dag_run**](DAGRunApi.md#get_dag_run) | **GET** /dags/{dag_id}/dagRuns/{dag_run_id} | Get a DAG run
[**get_dag_runs**](DAGRunApi.md#get_dag_runs) | **GET** /dags/{dag_id}/dagRuns | List DAG runs
[**get_dag_runs_batch**](DAGRunApi.md#get_dag_runs_batch) | **POST** /dags/~/dagRuns/list | List DAG runs (batch)
[**post_dag_run**](DAGRunApi.md#post_dag_run) | **POST** /dags/{dag_id}/dagRuns | Trigger a new DAG run
[**update_dag_run_state**](DAGRunApi.md#update_dag_run_state) | **PATCH** /dags/{dag_id}/dagRuns/{dag_run_id} | Modify a DAG run


# **delete_dag_run**
> delete_dag_run(dag_id, dag_run_id)

Delete a DAG run

### Example


```python
import time
import airflow_client.client
from airflow_client.client.api import dag_run_api
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
    api_instance = dag_run_api.DAGRunApi(api_client)
    dag_id = "dag_id_example" # str | The DAG ID.
    dag_run_id = "dag_run_id_example" # str | The DAG run ID.

    # example passing only required values which don't have defaults set
    try:
        # Delete a DAG run
        api_instance.delete_dag_run(dag_id, dag_run_id)
    except client.ApiException as e:
        print("Exception when calling DAGRunApi->delete_dag_run: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dag_id** | **str**| The DAG ID. |
 **dag_run_id** | **str**| The DAG run ID. |

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Success. |  -  |
**400** | Client specified an invalid argument. |  -  |
**401** | Request not authenticated due to missing, invalid, authentication info. |  -  |
**403** | Client does not have sufficient permission. |  -  |
**404** | A specified resource is not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_dag_run**
> DAGRun get_dag_run(dag_id, dag_run_id)

Get a DAG run

### Example


```python
import time
import airflow_client.client
from airflow_client.client.api import dag_run_api
from airflow_client.client.model.dag_run import DAGRun
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
    api_instance = dag_run_api.DAGRunApi(api_client)
    dag_id = "dag_id_example" # str | The DAG ID.
    dag_run_id = "dag_run_id_example" # str | The DAG run ID.

    # example passing only required values which don't have defaults set
    try:
        # Get a DAG run
        api_response = api_instance.get_dag_run(dag_id, dag_run_id)
        pprint(api_response)
    except client.ApiException as e:
        print("Exception when calling DAGRunApi->get_dag_run: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dag_id** | **str**| The DAG ID. |
 **dag_run_id** | **str**| The DAG run ID. |

### Return type

[**DAGRun**](DAGRun.md)

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
**404** | A specified resource is not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_dag_runs**
> DAGRunCollection get_dag_runs(dag_id)

List DAG runs

This endpoint allows specifying `~` as the dag_id to retrieve DAG runs for all DAGs. 

### Example


```python
import time
import airflow_client.client
from airflow_client.client.api import dag_run_api
from airflow_client.client.model.dag_run_collection import DAGRunCollection
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
    api_instance = dag_run_api.DAGRunApi(api_client)
    dag_id = "dag_id_example" # str | The DAG ID.
    limit = 100 # int | The numbers of items to return. (optional) if omitted the server will use the default value of 100
    offset = 0 # int | The number of items to skip before starting to collect the result set. (optional)
    execution_date_gte = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime | Returns objects greater or equal to the specified date.  This can be combined with execution_date_lte parameter to receive only the selected period.  (optional)
    execution_date_lte = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime | Returns objects less than or equal to the specified date.  This can be combined with execution_date_gte parameter to receive only the selected period.  (optional)
    start_date_gte = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime | Returns objects greater or equal the specified date.  This can be combined with start_date_lte parameter to receive only the selected period.  (optional)
    start_date_lte = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime | Returns objects less or equal the specified date.  This can be combined with start_date_gte parameter to receive only the selected period.  (optional)
    end_date_gte = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime | Returns objects greater or equal the specified date.  This can be combined with start_date_lte parameter to receive only the selected period.  (optional)
    end_date_lte = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime | Returns objects less than or equal to the specified date.  This can be combined with start_date_gte parameter to receive only the selected period.  (optional)
    order_by = "order_by_example" # str | The name of the field to order the results by. Prefix a field name with `-` to reverse the sort order.  (optional)

    # example passing only required values which don't have defaults set
    try:
        # List DAG runs
        api_response = api_instance.get_dag_runs(dag_id)
        pprint(api_response)
    except client.ApiException as e:
        print("Exception when calling DAGRunApi->get_dag_runs: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # List DAG runs
        api_response = api_instance.get_dag_runs(dag_id, limit=limit, offset=offset, execution_date_gte=execution_date_gte, execution_date_lte=execution_date_lte, start_date_gte=start_date_gte, start_date_lte=start_date_lte, end_date_gte=end_date_gte, end_date_lte=end_date_lte, order_by=order_by)
        pprint(api_response)
    except client.ApiException as e:
        print("Exception when calling DAGRunApi->get_dag_runs: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dag_id** | **str**| The DAG ID. |
 **limit** | **int**| The numbers of items to return. | [optional] if omitted the server will use the default value of 100
 **offset** | **int**| The number of items to skip before starting to collect the result set. | [optional]
 **execution_date_gte** | **datetime**| Returns objects greater or equal to the specified date.  This can be combined with execution_date_lte parameter to receive only the selected period.  | [optional]
 **execution_date_lte** | **datetime**| Returns objects less than or equal to the specified date.  This can be combined with execution_date_gte parameter to receive only the selected period.  | [optional]
 **start_date_gte** | **datetime**| Returns objects greater or equal the specified date.  This can be combined with start_date_lte parameter to receive only the selected period.  | [optional]
 **start_date_lte** | **datetime**| Returns objects less or equal the specified date.  This can be combined with start_date_gte parameter to receive only the selected period.  | [optional]
 **end_date_gte** | **datetime**| Returns objects greater or equal the specified date.  This can be combined with start_date_lte parameter to receive only the selected period.  | [optional]
 **end_date_lte** | **datetime**| Returns objects less than or equal to the specified date.  This can be combined with start_date_gte parameter to receive only the selected period.  | [optional]
 **order_by** | **str**| The name of the field to order the results by. Prefix a field name with &#x60;-&#x60; to reverse the sort order.  | [optional]

### Return type

[**DAGRunCollection**](DAGRunCollection.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of DAG runs. |  -  |
**401** | Request not authenticated due to missing, invalid, authentication info. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_dag_runs_batch**
> DAGRunCollection get_dag_runs_batch(list_dag_runs_form)

List DAG runs (batch)

This endpoint is a POST to allow filtering across a large number of DAG IDs, where as a GET it would run in to maximum HTTP request URL length limit. 

### Example


```python
import time
import airflow_client.client
from airflow_client.client.api import dag_run_api
from airflow_client.client.model.list_dag_runs_form import ListDagRunsForm
from airflow_client.client.model.dag_run_collection import DAGRunCollection
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
    api_instance = dag_run_api.DAGRunApi(api_client)
    list_dag_runs_form = ListDagRunsForm(
        dag_ids=[
            "dag_ids_example",
        ],
        end_date_gte=dateutil_parser('1970-01-01T00:00:00.00Z'),
        end_date_lte=dateutil_parser('1970-01-01T00:00:00.00Z'),
        execution_date_gte=dateutil_parser('1970-01-01T00:00:00.00Z'),
        execution_date_lte=dateutil_parser('1970-01-01T00:00:00.00Z'),
        order_by="order_by_example",
        page_limit=100,
        page_offset=0,
        start_date_gte=dateutil_parser('1970-01-01T00:00:00.00Z'),
        start_date_lte=dateutil_parser('1970-01-01T00:00:00.00Z'),
    ) # ListDagRunsForm | 

    # example passing only required values which don't have defaults set
    try:
        # List DAG runs (batch)
        api_response = api_instance.get_dag_runs_batch(list_dag_runs_form)
        pprint(api_response)
    except client.ApiException as e:
        print("Exception when calling DAGRunApi->get_dag_runs_batch: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **list_dag_runs_form** | [**ListDagRunsForm**](ListDagRunsForm.md)|  |

### Return type

[**DAGRunCollection**](DAGRunCollection.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success. |  -  |
**400** | Client specified an invalid argument. |  -  |
**401** | Request not authenticated due to missing, invalid, authentication info. |  -  |
**403** | Client does not have sufficient permission. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **post_dag_run**
> DAGRun post_dag_run(dag_id, dag_run)

Trigger a new DAG run

### Example


```python
import time
import airflow_client.client
from airflow_client.client.api import dag_run_api
from airflow_client.client.model.dag_run import DAGRun
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
    api_instance = dag_run_api.DAGRunApi(api_client)
    dag_id = "dag_id_example" # str | The DAG ID.
    dag_run = DAGRun(
        conf={},
        dag_run_id="dag_run_id_example",
        execution_date=dateutil_parser('1970-01-01T00:00:00.00Z'),
        logical_date=dateutil_parser('1970-01-01T00:00:00.00Z'),
        state=DagState("queued"),
    ) # DAGRun | 

    # example passing only required values which don't have defaults set
    try:
        # Trigger a new DAG run
        api_response = api_instance.post_dag_run(dag_id, dag_run)
        pprint(api_response)
    except client.ApiException as e:
        print("Exception when calling DAGRunApi->post_dag_run: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dag_id** | **str**| The DAG ID. |
 **dag_run** | [**DAGRun**](DAGRun.md)|  |

### Return type

[**DAGRun**](DAGRun.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success. |  -  |
**400** | Client specified an invalid argument. |  -  |
**401** | Request not authenticated due to missing, invalid, authentication info. |  -  |
**403** | Client does not have sufficient permission. |  -  |
**404** | A specified resource is not found. |  -  |
**409** | An existing resource conflicts with the request. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_dag_run_state**
> DAGRun update_dag_run_state(dag_id, dag_run_id, update_dag_run_state)

Modify a DAG run

Modify a DAG run

### Example


```python
import time
import airflow_client.client
from airflow_client.client.api import dag_run_api
from airflow_client.client.model.dag_run import DAGRun
from airflow_client.client.model.update_dag_run_state import UpdateDagRunState
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
    api_instance = dag_run_api.DAGRunApi(api_client)
    dag_id = "dag_id_example" # str | The DAG ID.
    dag_run_id = "dag_run_id_example" # str | The DAG run ID.
    update_dag_run_state = UpdateDagRunState(
        state="success",
    ) # UpdateDagRunState | 

    # example passing only required values which don't have defaults set
    try:
        # Modify a DAG run
        api_response = api_instance.update_dag_run_state(dag_id, dag_run_id, update_dag_run_state)
        pprint(api_response)
    except client.ApiException as e:
        print("Exception when calling DAGRunApi->update_dag_run_state: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dag_id** | **str**| The DAG ID. |
 **dag_run_id** | **str**| The DAG run ID. |
 **update_dag_run_state** | [**UpdateDagRunState**](UpdateDagRunState.md)|  |

### Return type

[**DAGRun**](DAGRun.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Success. |  -  |
**400** | Client specified an invalid argument. |  -  |
**401** | Request not authenticated due to missing, invalid, authentication info. |  -  |
**403** | Client does not have sufficient permission. |  -  |
**404** | A specified resource is not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

