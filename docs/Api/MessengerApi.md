# Swagger\Client\MessengerApi

All URIs are relative to *https://api.avito.ru/*

Method | HTTP request | Description
------------- | ------------- | -------------
[**chatRead**](MessengerApi.md#chatread) | **POST** /messenger/v1/accounts/{user_id}/chats/{chat_id}/read | Прочитать чат
[**deleteMessage**](MessengerApi.md#deletemessage) | **POST** /messenger/v1/accounts/{user_id}/chats/{chat_id}/messages/{message_id} | Удаление сообщения
[**getChatByIdV2**](MessengerApi.md#getchatbyidv2) | **GET** /messenger/v2/accounts/{user_id}/chats/{chat_id} | Получение информации по чату
[**getChatsV2**](MessengerApi.md#getchatsv2) | **GET** /messenger/v2/accounts/{user_id}/chats | Получение информации по чатам
[**getMessagesV3**](MessengerApi.md#getmessagesv3) | **GET** /messenger/v3/accounts/{user_id}/chats/{chat_id}/messages/ | Получение списка сообщений V3
[**getSubscriptions**](MessengerApi.md#getsubscriptions) | **POST** /messenger/v1/subscriptions | Получение подписок (webhooks)
[**postBlacklistV2**](MessengerApi.md#postblacklistv2) | **POST** /messenger/v2/accounts/{user_id}/blacklist | Добавление пользователя в blacklist
[**postSendMessage**](MessengerApi.md#postsendmessage) | **POST** /messenger/v1/accounts/{user_id}/chats/{chat_id}/messages | Отправление сообщения
[**postWebhookUnsubscribe**](MessengerApi.md#postwebhookunsubscribe) | **POST** /messenger/v1/webhook/unsubscribe | Отключение уведомлений (webhooks)
[**postWebhookV3**](MessengerApi.md#postwebhookv3) | **POST** /messenger/v3/webhook | Включение уведомлений V3 (webhooks)

# **chatRead**
> \Swagger\Client\Model\InlineResponse2001 chatRead($authorization, $user_id, $chat_id)

Прочитать чат

После успешного получения списка сообщений необходимо вызвать этот метод для того, чтобы чат стал прочитанным.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Идентификатор пользователя (клиента)
$chat_id = "chat_id_example"; // string | Идентификатор чата (клиента)

try {
    $result = $apiInstance->chatRead($authorization, $user_id, $chat_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->chatRead: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Идентификатор пользователя (клиента) |
 **chat_id** | **string**| Идентификатор чата (клиента) |

### Return type

[**\Swagger\Client\Model\InlineResponse2001**](../Model/InlineResponse2001.md)

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **deleteMessage**
> object deleteMessage($authorization, $user_id, $chat_id, $message_id)

Удаление сообщения

Сообщение не пропадает из истории, а меняет свой тип на deleted. Удалять сообщения можно не позднее часа с момента их отправки.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Идентификатор пользователя (клиента)
$chat_id = "chat_id_example"; // string | Идентификатор чата (клиента)
$message_id = "message_id_example"; // string | Идентификатор сообщения

try {
    $result = $apiInstance->deleteMessage($authorization, $user_id, $chat_id, $message_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->deleteMessage: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Идентификатор пользователя (клиента) |
 **chat_id** | **string**| Идентификатор чата (клиента) |
 **message_id** | **string**| Идентификатор сообщения |

### Return type

**object**

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getChatByIdV2**
> \Swagger\Client\Model\Chat getChatByIdV2($authorization, $user_id, $chat_id)

Получение информации по чату

Возвращает данные чата и последнее сообщение в нем

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Идентификатор пользователя (клиента)
$chat_id = "chat_id_example"; // string | Идентификатор чата (клиента)

try {
    $result = $apiInstance->getChatByIdV2($authorization, $user_id, $chat_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->getChatByIdV2: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Идентификатор пользователя (клиента) |
 **chat_id** | **string**| Идентификатор чата (клиента) |

### Return type

[**\Swagger\Client\Model\Chat**](../Model/Chat.md)

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getChatsV2**
> \Swagger\Client\Model\Chats getChatsV2($authorization, $user_id, $item_ids, $unread_only, $chat_types, $limit, $offset)

Получение информации по чатам

Возвращает список чатов

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Идентификатор пользователя (клиента)
$item_ids = array(56); // int[] | Получение чатов только по объявлениям с указанными item_id
$unread_only = false; // bool | При значении true метод возвращает только непрочитанные чаты
$chat_types = array("chat_types_example"); // string[] | Фильтрация возвращаемых чатов.  * u2i — чаты по объявлениям; * u2u — чаты между пользователями;
$limit = 100; // int | Количество сообщений / чатов для запроса
$offset = 0; // int | Сдвиг сообщений / чатов для запроса

try {
    $result = $apiInstance->getChatsV2($authorization, $user_id, $item_ids, $unread_only, $chat_types, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->getChatsV2: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Идентификатор пользователя (клиента) |
 **item_ids** | [**int[]**](../Model/int.md)| Получение чатов только по объявлениям с указанными item_id | [optional]
 **unread_only** | **bool**| При значении true метод возвращает только непрочитанные чаты | [optional] [default to false]
 **chat_types** | [**string[]**](../Model/string.md)| Фильтрация возвращаемых чатов.  * u2i — чаты по объявлениям; * u2u — чаты между пользователями; | [optional]
 **limit** | **int**| Количество сообщений / чатов для запроса | [optional] [default to 100]
 **offset** | **int**| Сдвиг сообщений / чатов для запроса | [optional] [default to 0]

### Return type

[**\Swagger\Client\Model\Chats**](../Model/Chats.md)

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getMessagesV3**
> \Swagger\Client\Model\Messages getMessagesV3($authorization, $user_id, $chat_id, $limit, $offset)

Получение списка сообщений V3

Получение списка сообщений.  **Не помечает чат прочитанным.** После успешного получения списка сообщений необходимо вызвать [метод](https://api.avito.ru/docs/api.html#operation/chatRead), который сделает сообщения прочитанными. Для получения новых сообщений в реальном времени используйте [webhooks](https://api.avito.ru/docs/api.html#operation/postWebhookV3)

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Идентификатор пользователя (клиента)
$chat_id = "chat_id_example"; // string | Идентификатор чата (клиента)
$limit = 100; // int | Количество сообщений / чатов для запроса
$offset = 0; // int | Сдвиг сообщений / чатов для запроса

try {
    $result = $apiInstance->getMessagesV3($authorization, $user_id, $chat_id, $limit, $offset);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->getMessagesV3: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Идентификатор пользователя (клиента) |
 **chat_id** | **string**| Идентификатор чата (клиента) |
 **limit** | **int**| Количество сообщений / чатов для запроса | [optional] [default to 100]
 **offset** | **int**| Сдвиг сообщений / чатов для запроса | [optional] [default to 0]

### Return type

[**\Swagger\Client\Model\Messages**](../Model/Messages.md)

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getSubscriptions**
> \Swagger\Client\Model\InlineResponse2002[] getSubscriptions($authorization)

Получение подписок (webhooks)

Получение списка подписок

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации

try {
    $result = $apiInstance->getSubscriptions($authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->getSubscriptions: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |

### Return type

[**\Swagger\Client\Model\InlineResponse2002[]**](../Model/InlineResponse2002.md)

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **postBlacklistV2**
> postBlacklistV2($authorization, $user_id, $body)

Добавление пользователя в blacklist

Добавление пользователя в blacklist

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Идентификатор пользователя (клиента)
$body = new \Swagger\Client\Model\AddBlacklistRequestBody(); // \Swagger\Client\Model\AddBlacklistRequestBody | Добавление пользователя в blacklist

try {
    $apiInstance->postBlacklistV2($authorization, $user_id, $body);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->postBlacklistV2: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Идентификатор пользователя (клиента) |
 **body** | [**\Swagger\Client\Model\AddBlacklistRequestBody**](../Model/AddBlacklistRequestBody.md)| Добавление пользователя в blacklist | [optional]

### Return type

void (empty response body)

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **postSendMessage**
> \Swagger\Client\Model\InlineResponse200 postSendMessage($authorization, $user_id, $chat_id, $body)

Отправление сообщения

На данный момент можно отправить только текстовое сообщение

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации
$user_id = 789; // int | Идентификатор пользователя (клиента)
$chat_id = "chat_id_example"; // string | Идентификатор чата (клиента)
$body = new \Swagger\Client\Model\SendMessageRequestBody(); // \Swagger\Client\Model\SendMessageRequestBody | Отправление сообщения

try {
    $result = $apiInstance->postSendMessage($authorization, $user_id, $chat_id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->postSendMessage: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **user_id** | **int**| Идентификатор пользователя (клиента) |
 **chat_id** | **string**| Идентификатор чата (клиента) |
 **body** | [**\Swagger\Client\Model\SendMessageRequestBody**](../Model/SendMessageRequestBody.md)| Отправление сообщения | [optional]

### Return type

[**\Swagger\Client\Model\InlineResponse200**](../Model/InlineResponse200.md)

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **postWebhookUnsubscribe**
> \Swagger\Client\Model\InlineResponse2001 postWebhookUnsubscribe($authorization, $body)

Отключение уведомлений (webhooks)

Отключение уведомлений

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации
$body = new \Swagger\Client\Model\WebhookSubscribeRequestBody(); // \Swagger\Client\Model\WebhookSubscribeRequestBody | Url, на который необходимо перестать слать уведомления

try {
    $result = $apiInstance->postWebhookUnsubscribe($authorization, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->postWebhookUnsubscribe: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **body** | [**\Swagger\Client\Model\WebhookSubscribeRequestBody**](../Model/WebhookSubscribeRequestBody.md)| Url, на который необходимо перестать слать уведомления | [optional]

### Return type

[**\Swagger\Client\Model\InlineResponse2001**](../Model/InlineResponse2001.md)

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **postWebhookV3**
> \Swagger\Client\Model\InlineResponse2001 postWebhookV3($authorization, $body)

Включение уведомлений V3 (webhooks)

Включение **V3** уведомлений.   Смотри схему JSON приходящего в webhook в примерах ответов <LINK_TO_V3_WEBHOOKS>.  Изменения в версии 3: * в дополнение к чатам типа u2i (по объявлениям) добавлена поддержка типа u2u (между пользователями); * внутри приходящего в webhook сообщения все поля, в которых мог содержаться id пользователя, теперь имеют   новое уникальное значение; оно не совпадает с id пользователя на основном сайте   и не может использоваться для сопоставления пользователей на сайте и в api; изменения коснулись только   id собеседников (ваш личный uid остался прежним);  После регистрации url'а для получения веб-хуков, убедитесь, что он доступен, работает и возвращает статус 200 ОК, например, выполнив запрос:  curl <url-вашего-вебхука> -i -d '{}'

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: AuthorizationCode
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure OAuth2 access token for authorization: ClientCredentials
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

$apiInstance = new Swagger\Client\Api\MessengerApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = "authorization_example"; // string | Токен для авторизации
$body = new \Swagger\Client\Model\WebhookSubscribeRequestBody(); // \Swagger\Client\Model\WebhookSubscribeRequestBody | Url на который будут отправляться уведомления

try {
    $result = $apiInstance->postWebhookV3($authorization, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MessengerApi->postWebhookV3: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| Токен для авторизации |
 **body** | [**\Swagger\Client\Model\WebhookSubscribeRequestBody**](../Model/WebhookSubscribeRequestBody.md)| Url на который будут отправляться уведомления | [optional]

### Return type

[**\Swagger\Client\Model\InlineResponse2001**](../Model/InlineResponse2001.md)

### Authorization

[AuthorizationCode](../../README.md#AuthorizationCode), [ClientCredentials](../../README.md#ClientCredentials)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

