# Task

For details see: (airflow.models.BaseOperator)[https://airflow.apache.org/docs/apache-airflow/stable/_api/airflow/models/index.html#airflow.models.BaseOperator] 

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**class_ref** | [**ClassReference**](ClassReference.md) |  | [optional] 
**depends_on_past** | **bool** |  | [optional] [readonly] 
**downstream_task_ids** | **[str]** |  | [optional] [readonly] 
**end_date** | **datetime, none_type** |  | [optional] [readonly] 
**execution_timeout** | [**TimeDelta**](TimeDelta.md) |  | [optional] 
**extra_links** | [**[TaskExtraLinks]**](TaskExtraLinks.md) |  | [optional] [readonly] 
**owner** | **str** |  | [optional] [readonly] 
**pool** | **str** |  | [optional] [readonly] 
**pool_slots** | **float** |  | [optional] [readonly] 
**priority_weight** | **float** |  | [optional] [readonly] 
**queue** | **str** |  | [optional] [readonly] 
**retries** | **float** |  | [optional] [readonly] 
**retry_delay** | [**TimeDelta**](TimeDelta.md) |  | [optional] 
**retry_exponential_backoff** | **bool** |  | [optional] [readonly] 
**start_date** | **datetime** |  | [optional] [readonly] 
**sub_dag** | [**DAG**](DAG.md) |  | [optional] 
**task_id** | **str** |  | [optional] [readonly] 
**template_fields** | **[str]** |  | [optional] [readonly] 
**trigger_rule** | [**TriggerRule**](TriggerRule.md) |  | [optional] 
**ui_color** | [**Color**](Color.md) |  | [optional] 
**ui_fgcolor** | [**Color**](Color.md) |  | [optional] 
**wait_for_downstream** | **bool** |  | [optional] [readonly] 
**weight_rule** | [**WeightRule**](WeightRule.md) |  | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


