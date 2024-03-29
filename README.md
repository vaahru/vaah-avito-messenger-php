# SwaggerClient-php
API Мессенджера - набор методов для получения списка чатов пользователя на Авито, получения сообщений в чате, отправки сообщения в чат и другие Через API Мессенджера можно организовать интеграцию между мессенджером Авито и сторонней системой в обе стороны  **Авито API для бизнеса предоставляется согласно [Условиям использования](https://www.avito.ru/legal/pro_tools/public-api).**

This PHP package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 1
- Build package: io.swagger.codegen.v3.generators.php.PhpClientCodegen

## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/vaahru/vaah-avito-messenger-php.git"
    }
  ],
  "require": {
    "vaahru/vaah-avito-messenger-php": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
    require_once('/path/to/SwaggerClient-php/vendor/autoload.php');
```

## Tests

To run the unit tests:

```
composer install
./vendor/bin/phpunit
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

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

## Documentation for API Endpoints

All URIs are relative to *https://api.avito.ru/*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*MessengerApi* | [**chatRead**](docs/Api/MessengerApi.md#chatread) | **POST** /messenger/v1/accounts/{user_id}/chats/{chat_id}/read | Прочитать чат
*MessengerApi* | [**deleteMessage**](docs/Api/MessengerApi.md#deletemessage) | **POST** /messenger/v1/accounts/{user_id}/chats/{chat_id}/messages/{message_id} | Удаление сообщения
*MessengerApi* | [**getChatByIdV2**](docs/Api/MessengerApi.md#getchatbyidv2) | **GET** /messenger/v2/accounts/{user_id}/chats/{chat_id} | Получение информации по чату
*MessengerApi* | [**getChatsV2**](docs/Api/MessengerApi.md#getchatsv2) | **GET** /messenger/v2/accounts/{user_id}/chats | Получение информации по чатам
*MessengerApi* | [**getMessagesV3**](docs/Api/MessengerApi.md#getmessagesv3) | **GET** /messenger/v3/accounts/{user_id}/chats/{chat_id}/messages/ | Получение списка сообщений V3
*MessengerApi* | [**getSubscriptions**](docs/Api/MessengerApi.md#getsubscriptions) | **POST** /messenger/v1/subscriptions | Получение подписок (webhooks)
*MessengerApi* | [**postBlacklistV2**](docs/Api/MessengerApi.md#postblacklistv2) | **POST** /messenger/v2/accounts/{user_id}/blacklist | Добавление пользователя в blacklist
*MessengerApi* | [**postSendMessage**](docs/Api/MessengerApi.md#postsendmessage) | **POST** /messenger/v1/accounts/{user_id}/chats/{chat_id}/messages | Отправление сообщения
*MessengerApi* | [**postWebhookUnsubscribe**](docs/Api/MessengerApi.md#postwebhookunsubscribe) | **POST** /messenger/v1/webhook/unsubscribe | Отключение уведомлений (webhooks)
*MessengerApi* | [**postWebhookV3**](docs/Api/MessengerApi.md#postwebhookv3) | **POST** /messenger/v3/webhook | Включение уведомлений V3 (webhooks)

## Documentation For Models

 - [AddBlacklistRequestBody](docs/Model/AddBlacklistRequestBody.md)
 - [AddBlacklistRequestBodyContext](docs/Model/AddBlacklistRequestBodyContext.md)
 - [AddBlacklistRequestBodyUsers](docs/Model/AddBlacklistRequestBodyUsers.md)
 - [AuthError](docs/Model/AuthError.md)
 - [AuthErrorError](docs/Model/AuthErrorError.md)
 - [BadRequestError](docs/Model/BadRequestError.md)
 - [BadRequestErrorError](docs/Model/BadRequestErrorError.md)
 - [Chat](docs/Model/Chat.md)
 - [ChatContext](docs/Model/ChatContext.md)
 - [ChatContextValue](docs/Model/ChatContextValue.md)
 - [ChatContextValueImages](docs/Model/ChatContextValueImages.md)
 - [ChatContextValueImagesMain](docs/Model/ChatContextValueImagesMain.md)
 - [ChatLastMessage](docs/Model/ChatLastMessage.md)
 - [ChatLastMessageContent](docs/Model/ChatLastMessageContent.md)
 - [ChatLastMessageContentLink](docs/Model/ChatLastMessageContentLink.md)
 - [ChatPublicUserProfile](docs/Model/ChatPublicUserProfile.md)
 - [ChatPublicUserProfileAvatar](docs/Model/ChatPublicUserProfileAvatar.md)
 - [ChatPublicUserProfileAvatarImages](docs/Model/ChatPublicUserProfileAvatarImages.md)
 - [ChatUsers](docs/Model/ChatUsers.md)
 - [Chats](docs/Model/Chats.md)
 - [ForbiddenError](docs/Model/ForbiddenError.md)
 - [ForbiddenErrorError](docs/Model/ForbiddenErrorError.md)
 - [InlineResponse200](docs/Model/InlineResponse200.md)
 - [InlineResponse2001](docs/Model/InlineResponse2001.md)
 - [InlineResponse2002](docs/Model/InlineResponse2002.md)
 - [InlineResponse200Content](docs/Model/InlineResponse200Content.md)
 - [MessageContent](docs/Model/MessageContent.md)
 - [MessageContentCall](docs/Model/MessageContentCall.md)
 - [MessageContentImage](docs/Model/MessageContentImage.md)
 - [MessageContentItem](docs/Model/MessageContentItem.md)
 - [MessageContentLink](docs/Model/MessageContentLink.md)
 - [MessageContentLinkPreview](docs/Model/MessageContentLinkPreview.md)
 - [MessageContentLocation](docs/Model/MessageContentLocation.md)
 - [MessageQuote](docs/Model/MessageQuote.md)
 - [Messages](docs/Model/Messages.md)
 - [MessagesInner](docs/Model/MessagesInner.md)
 - [NotFoundError](docs/Model/NotFoundError.md)
 - [NotFoundErrorError](docs/Model/NotFoundErrorError.md)
 - [PurchasingError](docs/Model/PurchasingError.md)
 - [PurchasingErrorError](docs/Model/PurchasingErrorError.md)
 - [SendMessageRequestBody](docs/Model/SendMessageRequestBody.md)
 - [SendMessageRequestBodyMessage](docs/Model/SendMessageRequestBodyMessage.md)
 - [ServiceError](docs/Model/ServiceError.md)
 - [ServiceErrorError](docs/Model/ServiceErrorError.md)
 - [ServiceUnavailableError](docs/Model/ServiceUnavailableError.md)
 - [ServiceUnavailableErrorError](docs/Model/ServiceUnavailableErrorError.md)
 - [ValidatingError](docs/Model/ValidatingError.md)
 - [ValidatingErrorError](docs/Model/ValidatingErrorError.md)
 - [WebhookMessage](docs/Model/WebhookMessage.md)
 - [WebhookSubscribeRequestBody](docs/Model/WebhookSubscribeRequestBody.md)

## Documentation For Authorization


## AuthorizationCode

- **Type**: OAuth
- **Flow**: accessCode
- **Authorization URL**: https://avito.ru/oauth
- **Scopes**: 
 - **autoload:reports**: Получение отчетов Автозагрузки
 - **items:apply_vas**: Применение дополнительных услуг
 - **items:info**: Получение информации об объявлениях
 - **job:applications**: Получение информации об откликах на вакансии
 - **job:cv**: Получение информации резюме
 - **job:write**: Изменение объявлений вертикали Работа
 - **messenger:read**: Чтение сообщений в мессенджере Авито
 - **messenger:write**: Модифицирование сообщений в мессенджере Авито
 - **short_term_rent:read**: Получение информации об объявлениях краткосрочной аренды
 - **short_term_rent:write**: Изменение объявлений краткосрочной аренды
 - **stats:read**: Получение статистики объявлений
 - **user:read**: Получение информации о пользователе
 - **user_balance:read**: Получение баланса пользователя
 - **user_operations:read**: Получение истории операций пользователя

## ClientCredentials

- **Type**: OAuth
- **Flow**: application
- **Authorization URL**: 
- **Scopes**: 


## Author

supportautoload@avito.ru

