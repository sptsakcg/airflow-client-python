# ClearTaskInstance


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**dry_run** | **bool** | If set, don&#39;t actually run this operation. The response will contain a list of task instances planned to be cleaned, but not modified in any way.  | [optional]  if omitted the server will use the default value of True
**end_date** | **str** | The maximum execution date to clear. | [optional] 
**include_parentdag** | **bool** | Clear tasks in the parent dag of the subdag. | [optional] 
**include_subdags** | **bool** | Clear tasks in subdags and clear external tasks indicated by ExternalTaskMarker. | [optional] 
**only_failed** | **bool** | Only clear failed tasks. | [optional]  if omitted the server will use the default value of True
**only_running** | **bool** | Only clear running tasks. | [optional]  if omitted the server will use the default value of False
**reset_dag_runs** | **bool** | Set state of DAG runs to RUNNING. | [optional] 
**start_date** | **str** | The minimum execution date to clear. | [optional] 
**task_ids** | **[str]** | A list of task ids to clear. | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


