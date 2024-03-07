# WebhookMessage

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**author_id** | **int** | id отправителя (ваш или собеседник) | [optional] 
**chat_id** | **string** |  | [optional] 
**chat_type** | **string** | Тип чата (u2i - чат по объявлению, u2u - чат по профилю пользователя) | [optional] 
**content** | [**\Swagger\Client\Model\MessageContent**](MessageContent.md) |  | [optional] 
**created** | **int** | timestamp отправки сообщения | [optional] 
**id** | **string** |  | [optional] 
**item_id** | **int** | id объявления в u2i-чате по которому пришло сообщение | [optional] 
**read** | **int** | timestamp прочтения, если прочитано | [optional] 
**type** | **string** | Тип сообщения | [optional] 
**user_id** | **int** | id получателя (текущий аккаунт) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

