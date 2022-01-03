# OpenAPI\Client\PointOfInterestApi

All URIs are relative to http://flyoapi-web-api.dev.heartbeat.gmbh:7171/sdk.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getPointsOfInterestPool()**](PointOfInterestApi.md#getPointsOfInterestPool) | **GET** /pools/172 | Points of Interest
[**viewPointsOfInterestPool()**](PointOfInterestApi.md#viewPointsOfInterestPool) | **GET** /pools/172/{id} | Points of Interest View


## `getPointsOfInterestPool()`

```php
getPointsOfInterestPool($page, $per_page, $sort, $filter): \OpenAPI\Client\Model\PointsOfInterestPool[]
```

Points of Interest

Alle Einträge

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (AuthToken) authorization: bearerAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\PointOfInterestApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$page = 2; // int | Pagination Page ID, by default page 1 is returned. Pagination starts at 1
$per_page = 1; // int | The number of items which should be returned per page, max is 100. By default its 25 items
$sort = id; // string | Certain content pools can be sorted, if sorting is enabled its possible to define `?sort=id` ASC (A-Z or 1-9) or for opposite sort `?sort=-id` DESC (Z-A or 9-1). Sorting multiple items can be achieved by seperating by comma `?sort=created_at,updated_at`
$filter = array('key' => new \stdClass); // object | Allows you to pass filtering options any attribute. `?filter[id]=123` or `?filter[author][like]=John`. Example of accessing nested array values `?filter[tags.alias]=food`

try {
    $result = $apiInstance->getPointsOfInterestPool($page, $per_page, $sort, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PointOfInterestApi->getPointsOfInterestPool: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **int**| Pagination Page ID, by default page 1 is returned. Pagination starts at 1 | [optional]
 **per_page** | **int**| The number of items which should be returned per page, max is 100. By default its 25 items | [optional]
 **sort** | **string**| Certain content pools can be sorted, if sorting is enabled its possible to define &#x60;?sort&#x3D;id&#x60; ASC (A-Z or 1-9) or for opposite sort &#x60;?sort&#x3D;-id&#x60; DESC (Z-A or 9-1). Sorting multiple items can be achieved by seperating by comma &#x60;?sort&#x3D;created_at,updated_at&#x60; | [optional]
 **filter** | [**object**](../Model/.md)| Allows you to pass filtering options any attribute. &#x60;?filter[id]&#x3D;123&#x60; or &#x60;?filter[author][like]&#x3D;John&#x60;. Example of accessing nested array values &#x60;?filter[tags.alias]&#x3D;food&#x60; | [optional]

### Return type

[**\OpenAPI\Client\Model\PointsOfInterestPool[]**](../Model/PointsOfInterestPool.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `viewPointsOfInterestPool()`

```php
viewPointsOfInterestPool($id, $fields): \OpenAPI\Client\Model\PointsOfInterestPool
```

Points of Interest View

View a certain item id from the pool items

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (AuthToken) authorization: bearerAuth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\PointOfInterestApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 2; // int | The row id to view
$fields = id,firstname,lastname; // string | In order to reduce the http transfer content size, its possible to define `?fields=id,firstname,lasstname` which are part of the response. Any other field will not be returned, except of metric, which is always present.

try {
    $result = $apiInstance->viewPointsOfInterestPool($id, $fields);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PointOfInterestApi->viewPointsOfInterestPool: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The row id to view |
 **fields** | **string**| In order to reduce the http transfer content size, its possible to define &#x60;?fields&#x3D;id,firstname,lasstname&#x60; which are part of the response. Any other field will not be returned, except of metric, which is always present. | [optional]

### Return type

[**\OpenAPI\Client\Model\PointsOfInterestPool**](../Model/PointsOfInterestPool.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
