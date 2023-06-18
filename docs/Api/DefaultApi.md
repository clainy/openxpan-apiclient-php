# Clainy\OpenxpanApiClient\DefaultApi

All URIs are relative to https://pan.baidu.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**apiCategoryinfo()**](DefaultApi.md#apiCategoryinfo) | **GET** /api/categoryinfo | 获取分类文件总个数 |
| [**apiQuota()**](DefaultApi.md#apiQuota) | **GET** /api/quota | 获取网盘容量信息 |
| [**pcsSuperfile2Upload()**](DefaultApi.md#pcsSuperfile2Upload) | **POST** /rest/2.0/pcs/superfile2?method=upload | 分片上传 |
| [**xpanFileBtlist()**](DefaultApi.md#xpanFileBtlist) | **GET** /rest/2.0/xpan/file?method=btlist | 获取bt列表 |
| [**xpanFileCreate()**](DefaultApi.md#xpanFileCreate) | **POST** /rest/2.0/xpan/file?method=create | 创建文件, 创建文件夹 |
| [**xpanFileDoclist()**](DefaultApi.md#xpanFileDoclist) | **GET** /rest/2.0/xpan/file?method=doclist | 获取文档列表 |
| [**xpanFileFilemanager()**](DefaultApi.md#xpanFileFilemanager) | **POST** /rest/2.0/xpan/file?method=filemanager | 管理文件 |
| [**xpanFileImagelist()**](DefaultApi.md#xpanFileImagelist) | **GET** /rest/2.0/xpan/file?method=imagelist | 获取图片列表 |
| [**xpanFileList()**](DefaultApi.md#xpanFileList) | **GET** /rest/2.0/xpan/file?method=list | 获取文件列表 |
| [**xpanFilePrecreate()**](DefaultApi.md#xpanFilePrecreate) | **POST** /rest/2.0/xpan/file?method=precreate | 预上传 |
| [**xpanFileSearch()**](DefaultApi.md#xpanFileSearch) | **GET** /rest/2.0/xpan/file?method=search | 搜索文件 |
| [**xpanFileVideolist()**](DefaultApi.md#xpanFileVideolist) | **GET** /rest/2.0/xpan/file?method=videolist | 获取视频列表 |
| [**xpanMultimediaCategorylist()**](DefaultApi.md#xpanMultimediaCategorylist) | **GET** /rest/2.0/xpan/multimedia?method=categorylist | 获取分类文件列表 |
| [**xpanMultimediaFilemetas()**](DefaultApi.md#xpanMultimediaFilemetas) | **GET** /rest/2.0/xpan/multimedia?method=filemetas | 查询文件信息 |
| [**xpanMultimediaListall()**](DefaultApi.md#xpanMultimediaListall) | **GET** /rest/2.0/xpan/multimedia?method=listall | 递归获取文件列表 |
| [**xpanNasUinfo()**](DefaultApi.md#xpanNasUinfo) | **GET** /rest/2.0/xpan/nas?method=uinfo | 获取用户信息 |


## `apiCategoryinfo()`

```php
apiCategoryinfo($parent_path, $recursion, $category): \Clainy\OpenxpanApiClient\Model\ApiCategoryinfo200Response
```

获取分类文件总个数

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$parent_path = 'parent_path_example'; // string | 目录名称，为空时，parent_path = \"/\" && recursion = 1
$recursion = 56; // int | 是否递归，0 不递归、1 递归，默认0
$category = 56; // int | 文件类型，1 视频、2 音频、3 图片、4 文档、5 应用、6 其他、7 种子

try {
    $result = $apiInstance->apiCategoryinfo($parent_path, $recursion, $category);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->apiCategoryinfo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **parent_path** | **string**| 目录名称，为空时，parent_path &#x3D; \&quot;/\&quot; &amp;&amp; recursion &#x3D; 1 | |
| **recursion** | **int**| 是否递归，0 不递归、1 递归，默认0 | |
| **category** | **int**| 文件类型，1 视频、2 音频、3 图片、4 文档、5 应用、6 其他、7 种子 | [optional] |

### Return type

[**\Clainy\OpenxpanApiClient\Model\ApiCategoryinfo200Response**](../Model/ApiCategoryinfo200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `apiQuota()`

```php
apiQuota($checkfree, $checkexpire): \Clainy\OpenxpanApiClient\Model\ApiQuota200Response
```

获取网盘容量信息

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$checkfree = 56; // int | 是否检查免费信息，0为不查，1为查，默认为0
$checkexpire = 56; // int | 是否检查过期信息，0为不查，1为查，默认为0

try {
    $result = $apiInstance->apiQuota($checkfree, $checkexpire);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->apiQuota: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **checkfree** | **int**| 是否检查免费信息，0为不查，1为查，默认为0 | |
| **checkexpire** | **int**| 是否检查过期信息，0为不查，1为查，默认为0 | |

### Return type

[**\Clainy\OpenxpanApiClient\Model\ApiQuota200Response**](../Model/ApiQuota200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `pcsSuperfile2Upload()`

```php
pcsSuperfile2Upload($type, $path, $uploadid, $partseq, $post_pcs_superfile2_upload): \Clainy\OpenxpanApiClient\Model\PcsSuperfile2Upload200Response
```

分片上传

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$type = 'type_example'; // string | 固定值 tmpfile
$path = 'path_example'; // string | 上传后使用的文件绝对路径，需要urlencode，需要与上一个阶段预上传precreate接口中的path保持一致
$uploadid = 'uploadid_example'; // string | 上一个阶段预上传precreate接口下发的uploadid
$partseq = 56; // int | 文件分片的位置序号，从0开始，参考上一个阶段预上传precreate接口返回的block_list
$post_pcs_superfile2_upload = new \Clainy\OpenxpanApiClient\Model\PostPcsSuperfile2Upload(); // \Clainy\OpenxpanApiClient\Model\PostPcsSuperfile2Upload

try {
    $result = $apiInstance->pcsSuperfile2Upload($type, $path, $uploadid, $partseq, $post_pcs_superfile2_upload);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->pcsSuperfile2Upload: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **type** | **string**| 固定值 tmpfile | [optional] |
| **path** | **string**| 上传后使用的文件绝对路径，需要urlencode，需要与上一个阶段预上传precreate接口中的path保持一致 | [optional] |
| **uploadid** | **string**| 上一个阶段预上传precreate接口下发的uploadid | [optional] |
| **partseq** | **int**| 文件分片的位置序号，从0开始，参考上一个阶段预上传precreate接口返回的block_list | [optional] |
| **post_pcs_superfile2_upload** | [**\Clainy\OpenxpanApiClient\Model\PostPcsSuperfile2Upload**](../Model/PostPcsSuperfile2Upload.md)|  | [optional] |

### Return type

[**\Clainy\OpenxpanApiClient\Model\PcsSuperfile2Upload200Response**](../Model/PcsSuperfile2Upload200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanFileBtlist()`

```php
xpanFileBtlist($parent_path, $page, $num, $order, $desc, $recursion): \Clainy\OpenxpanApiClient\Model\XpanFileDoclist200Response
```

获取bt列表

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$parent_path = 'parent_path_example'; // string | 目录名称，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码
$page = 56; // int | 页码，从1开始， 如果不指定页码，则为不分页模式，返回所有的结果。如果指定page参数，则按修改时间倒序排列
$num = 56; // int | 每页返回的文件数， 默认值为1000, 最大值建议不超过1000
$order = 'order_example'; // string | 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time
$desc = 'desc_example'; // string | 0为升序，1为降序，默认为1
$recursion = 56; // int | 是否需要递归，0为不需要，1为需要，默认为0 递归是指：当目录下有文件夹，使用此参数，可以获取到文件夹下面的bt文件

try {
    $result = $apiInstance->xpanFileBtlist($parent_path, $page, $num, $order, $desc, $recursion);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanFileBtlist: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **parent_path** | **string**| 目录名称，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码 | |
| **page** | **int**| 页码，从1开始， 如果不指定页码，则为不分页模式，返回所有的结果。如果指定page参数，则按修改时间倒序排列 | |
| **num** | **int**| 每页返回的文件数， 默认值为1000, 最大值建议不超过1000 | |
| **order** | **string**| 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time | |
| **desc** | **string**| 0为升序，1为降序，默认为1 | |
| **recursion** | **int**| 是否需要递归，0为不需要，1为需要，默认为0 递归是指：当目录下有文件夹，使用此参数，可以获取到文件夹下面的bt文件 | |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanFileDoclist200Response**](../Model/XpanFileDoclist200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanFileCreate()`

```php
xpanFileCreate($post_xpan_file_create): \Clainy\OpenxpanApiClient\Model\XpanFileCreate200Response
```

创建文件, 创建文件夹

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_xpan_file_create = new \Clainy\OpenxpanApiClient\Model\PostXpanFileCreate(); // \Clainy\OpenxpanApiClient\Model\PostXpanFileCreate

try {
    $result = $apiInstance->xpanFileCreate($post_xpan_file_create);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanFileCreate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_xpan_file_create** | [**\Clainy\OpenxpanApiClient\Model\PostXpanFileCreate**](../Model/PostXpanFileCreate.md)|  | [optional] |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanFileCreate200Response**](../Model/XpanFileCreate200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanFileDoclist()`

```php
xpanFileDoclist($parent_path, $page, $num, $order, $desc, $recursion, $web): \Clainy\OpenxpanApiClient\Model\XpanFileDoclist200Response
```

获取文档列表

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$parent_path = 'parent_path_example'; // string | 目录名称，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码。
$page = 56; // int | 页码，从1开始， 如果不指定页码，则为不分页模式，返回所有的结果。如果指定page参数，则按修改时间倒序排列
$num = 56; // int | 一页返回的文档数， 默认值为1000，建议最大值不超过1000
$order = 'order_example'; // string | 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time
$desc = 'desc_example'; // string | 0为升序，1为降序，默认为1
$recursion = 56; // int | 是否需要递归，0为不需要，1为需要，默认为0 递归是指：当目录下有文件夹，使用此参数，可以获取到文件夹下面的文档
$web = 56; // int | 为1时返回文档预览地址lodocpreview

try {
    $result = $apiInstance->xpanFileDoclist($parent_path, $page, $num, $order, $desc, $recursion, $web);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanFileDoclist: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **parent_path** | **string**| 目录名称，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码。 | |
| **page** | **int**| 页码，从1开始， 如果不指定页码，则为不分页模式，返回所有的结果。如果指定page参数，则按修改时间倒序排列 | |
| **num** | **int**| 一页返回的文档数， 默认值为1000，建议最大值不超过1000 | |
| **order** | **string**| 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time | |
| **desc** | **string**| 0为升序，1为降序，默认为1 | |
| **recursion** | **int**| 是否需要递归，0为不需要，1为需要，默认为0 递归是指：当目录下有文件夹，使用此参数，可以获取到文件夹下面的文档 | |
| **web** | **int**| 为1时返回文档预览地址lodocpreview | |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanFileDoclist200Response**](../Model/XpanFileDoclist200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanFileFilemanager()`

```php
xpanFileFilemanager($opera, $post_xpan_file_filemanager): \Clainy\OpenxpanApiClient\Model\XpanFileFilemanager200Response
```

管理文件

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$opera = 'opera_example'; // string | 文件操作参数，可实现文件复制、移动、重命名、删除，依次对应的参数值为：copy、move、rename、delete
$post_xpan_file_filemanager = new \Clainy\OpenxpanApiClient\Model\PostXpanFileFilemanager(); // \Clainy\OpenxpanApiClient\Model\PostXpanFileFilemanager

try {
    $result = $apiInstance->xpanFileFilemanager($opera, $post_xpan_file_filemanager);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanFileFilemanager: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **opera** | **string**| 文件操作参数，可实现文件复制、移动、重命名、删除，依次对应的参数值为：copy、move、rename、delete | [optional] |
| **post_xpan_file_filemanager** | [**\Clainy\OpenxpanApiClient\Model\PostXpanFileFilemanager**](../Model/PostXpanFileFilemanager.md)|  | [optional] |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanFileFilemanager200Response**](../Model/XpanFileFilemanager200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanFileImagelist()`

```php
xpanFileImagelist($parent_path, $page, $num, $order, $desc, $recursion, $web): \Clainy\OpenxpanApiClient\Model\XpanFileDoclist200Response
```

获取图片列表

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$parent_path = 'parent_path_example'; // string | 目录名称，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码
$page = 56; // int | 页码，从1开始， 如果不指定页码，则为不分页模式，返回所有的结果 如果指定page参数，则按修改时间倒序排列
$num = 56; // int | 一页返回的图片数，默认值为1000，建议最大值不超过1000
$order = 'order_example'; // string | 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time
$desc = 'desc_example'; // string | 0为升序，1为降序，默认为1
$recursion = 56; // int | 是否需要递归，0为不需要，1为需要，默认为0 递归是指：当目录下有文件夹，使用此参数，可以获取到文件夹下面的图片
$web = 56; // int | 为1时返回图片缩略图

try {
    $result = $apiInstance->xpanFileImagelist($parent_path, $page, $num, $order, $desc, $recursion, $web);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanFileImagelist: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **parent_path** | **string**| 目录名称，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码 | |
| **page** | **int**| 页码，从1开始， 如果不指定页码，则为不分页模式，返回所有的结果 如果指定page参数，则按修改时间倒序排列 | |
| **num** | **int**| 一页返回的图片数，默认值为1000，建议最大值不超过1000 | |
| **order** | **string**| 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time | |
| **desc** | **string**| 0为升序，1为降序，默认为1 | |
| **recursion** | **int**| 是否需要递归，0为不需要，1为需要，默认为0 递归是指：当目录下有文件夹，使用此参数，可以获取到文件夹下面的图片 | |
| **web** | **int**| 为1时返回图片缩略图 | |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanFileDoclist200Response**](../Model/XpanFileDoclist200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanFileList()`

```php
xpanFileList($dir, $order, $desc, $start, $limit, $web, $folder, $showempty): \Clainy\OpenxpanApiClient\Model\XpanFileList200Response
```

获取文件列表

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dir = 'dir_example'; // string | 需要list的目录，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码
$order = 'order_example'; // string | 排序字段：默认为name；time表示先按文件类型排序，后按修改时间排序；name表示先按文件类型排序，后按文件名称排序；size表示先按文件类型排序，后按文件大小排序。
$desc = 56; // int | 默认为升序，设置为1实现降序 （注：排序的对象是当前目录下所有文件，不是当前分页下的文件）
$start = 56; // int | 起始位置，从0开始
$limit = 56; // int | 查询数目，默认为1000，建议最大不超过1000
$web = 56; // int | 值为1时，返回dir_empty属性和缩略图数据
$folder = 56; // int | 是否只返回文件夹，0 返回所有，1 只返回文件夹，且属性只返回path字段
$showempty = 56; // int | 是否返回dir_empty属性，0 不返回，1 返回

try {
    $result = $apiInstance->xpanFileList($dir, $order, $desc, $start, $limit, $web, $folder, $showempty);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanFileList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dir** | **string**| 需要list的目录，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码 | |
| **order** | **string**| 排序字段：默认为name；time表示先按文件类型排序，后按修改时间排序；name表示先按文件类型排序，后按文件名称排序；size表示先按文件类型排序，后按文件大小排序。 | |
| **desc** | **int**| 默认为升序，设置为1实现降序 （注：排序的对象是当前目录下所有文件，不是当前分页下的文件） | |
| **start** | **int**| 起始位置，从0开始 | |
| **limit** | **int**| 查询数目，默认为1000，建议最大不超过1000 | |
| **web** | **int**| 值为1时，返回dir_empty属性和缩略图数据 | |
| **folder** | **int**| 是否只返回文件夹，0 返回所有，1 只返回文件夹，且属性只返回path字段 | |
| **showempty** | **int**| 是否返回dir_empty属性，0 不返回，1 返回 | |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanFileList200Response**](../Model/XpanFileList200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanFilePrecreate()`

```php
xpanFilePrecreate($post_xpan_file_precreate): \Clainy\OpenxpanApiClient\Model\XpanFilePrecreate200Response
```

预上传

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_xpan_file_precreate = new \Clainy\OpenxpanApiClient\Model\PostXpanFilePrecreate(); // \Clainy\OpenxpanApiClient\Model\PostXpanFilePrecreate

try {
    $result = $apiInstance->xpanFilePrecreate($post_xpan_file_precreate);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanFilePrecreate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_xpan_file_precreate** | [**\Clainy\OpenxpanApiClient\Model\PostXpanFilePrecreate**](../Model/PostXpanFilePrecreate.md)|  | [optional] |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanFilePrecreate200Response**](../Model/XpanFilePrecreate200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanFileSearch()`

```php
xpanFileSearch($dir, $page, $num, $recursion, $web, $device_id, $key): \Clainy\OpenxpanApiClient\Model\XpanFileSearch200Response
```

搜索文件

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dir = 'dir_example'; // string | 搜索目录，默认根目录
$page = 56; // int | 页数，从1开始，缺省则返回所有条目
$num = 56; // int | 默认为500，不能修改
$recursion = 56; // int | 是否递归搜索子目录 1:是，0:否（默认）
$web = 56; // int | 默认0，为1时返回缩略图信息
$device_id = 'device_id_example'; // string | 设备ID，设备注册接口下发，硬件设备必传
$key = 'key_example'; // string | 搜索关键字，最大30字符（UTF8格式）

try {
    $result = $apiInstance->xpanFileSearch($dir, $page, $num, $recursion, $web, $device_id, $key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanFileSearch: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dir** | **string**| 搜索目录，默认根目录 | |
| **page** | **int**| 页数，从1开始，缺省则返回所有条目 | |
| **num** | **int**| 默认为500，不能修改 | |
| **recursion** | **int**| 是否递归搜索子目录 1:是，0:否（默认） | |
| **web** | **int**| 默认0，为1时返回缩略图信息 | |
| **device_id** | **string**| 设备ID，设备注册接口下发，硬件设备必传 | |
| **key** | **string**| 搜索关键字，最大30字符（UTF8格式） | [optional] |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanFileSearch200Response**](../Model/XpanFileSearch200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanFileVideolist()`

```php
xpanFileVideolist($parent_path, $page, $num, $order, $desc, $recursion, $web): \Clainy\OpenxpanApiClient\Model\XpanFileDoclist200Response
```

获取视频列表

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$parent_path = 'parent_path_example'; // string | 目录名称，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码
$page = 56; // int | 页码，从1开始， 如果不指定页码，则为不分页模式，返回所有的结果。如果指定page参数，则按修改时间倒序排列
$num = 56; // int | 一页返回的文件数， 默认值为1000, 最大值建议不超过1000
$order = 'order_example'; // string | 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time
$desc = 'desc_example'; // string | 0为升序，1为降序，默认为1
$recursion = 56; // int | 是否需要递归，0为不需要，1为需要，默认为0 递归是指：当目录下有文件夹，使用此参数，可以获取到文件夹下面的视频
$web = 56; // int | 为1时返回视频预览缩略图

try {
    $result = $apiInstance->xpanFileVideolist($parent_path, $page, $num, $order, $desc, $recursion, $web);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanFileVideolist: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **parent_path** | **string**| 目录名称，以/开头的绝对路径, 默认为/ 路径包含中文时需要UrlEncode编码 给出的示例的路径是/测试目录的UrlEncode编码 | |
| **page** | **int**| 页码，从1开始， 如果不指定页码，则为不分页模式，返回所有的结果。如果指定page参数，则按修改时间倒序排列 | |
| **num** | **int**| 一页返回的文件数， 默认值为1000, 最大值建议不超过1000 | |
| **order** | **string**| 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time | |
| **desc** | **string**| 0为升序，1为降序，默认为1 | |
| **recursion** | **int**| 是否需要递归，0为不需要，1为需要，默认为0 递归是指：当目录下有文件夹，使用此参数，可以获取到文件夹下面的视频 | |
| **web** | **int**| 为1时返回视频预览缩略图 | |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanFileDoclist200Response**](../Model/XpanFileDoclist200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanMultimediaCategorylist()`

```php
xpanMultimediaCategorylist($show_dir, $parent_path, $recursion, $ext, $start, $limit, $order, $desc, $category): \Clainy\OpenxpanApiClient\Model\XpanMultimediaCategorylist200Response
```

获取分类文件列表

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$show_dir = 56; // int | 是否展示文件夹，0:否(默认) 1:是
$parent_path = 'parent_path_example'; // string | 目录名称，为空时，parent_path = \"/\" && recursion = 1 ；路径包含中文时需要进行UrlEncode编码
$recursion = 56; // int | 是否需要递归，0 不递归、1 递归，默认0
$ext = 'ext_example'; // string | 需要的文件格式，多个格式以英文逗号分隔，示例: txt,epub，默认为category下所有格式
$start = 56; // int | 查询起点，默认为0
$limit = 56; // int | 查询数目，最大1000，默认1000
$order = 'order_example'; // string | 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time
$desc = 'desc_example'; // string | 0为升序，1为降序，默认为1
$category = 56; // int | 文件类型，1 视频、2 音频、3 图片、4 文档、5 应用、6 其他、7 种子多个category使用英文逗号分隔，示例：3,4

try {
    $result = $apiInstance->xpanMultimediaCategorylist($show_dir, $parent_path, $recursion, $ext, $start, $limit, $order, $desc, $category);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanMultimediaCategorylist: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **show_dir** | **int**| 是否展示文件夹，0:否(默认) 1:是 | |
| **parent_path** | **string**| 目录名称，为空时，parent_path &#x3D; \&quot;/\&quot; &amp;&amp; recursion &#x3D; 1 ；路径包含中文时需要进行UrlEncode编码 | |
| **recursion** | **int**| 是否需要递归，0 不递归、1 递归，默认0 | |
| **ext** | **string**| 需要的文件格式，多个格式以英文逗号分隔，示例: txt,epub，默认为category下所有格式 | |
| **start** | **int**| 查询起点，默认为0 | |
| **limit** | **int**| 查询数目，最大1000，默认1000 | |
| **order** | **string**| 排序字段：time按修改时间排序，name按文件名称排序，size按文件大小排序，默认为time | |
| **desc** | **string**| 0为升序，1为降序，默认为1 | |
| **category** | **int**| 文件类型，1 视频、2 音频、3 图片、4 文档、5 应用、6 其他、7 种子多个category使用英文逗号分隔，示例：3,4 | [optional] |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanMultimediaCategorylist200Response**](../Model/XpanMultimediaCategorylist200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanMultimediaFilemetas()`

```php
xpanMultimediaFilemetas($dlink, $path, $thumb, $extra, $needmedia, $fsids): \Clainy\OpenxpanApiClient\Model\XpanMultimediaFilemetas200Response
```

查询文件信息

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$dlink = 56; // int | 是否需要下载地址，0为否，1为是，默认为0。获取到dlink后，参考下载文档进行下载操作
$path = 'path_example'; // string | 查询共享目录或专属空间内文件时需要。共享目录格式： /uk-fsid 其中uk为共享目录创建者id， fsid对应共享目录的fsid 专属空间格式：/_pcs_.appdata/xpan/
$thumb = 56; // int | 是否需要缩略图地址，0为否，1为是，默认为0
$extra = 56; // int | 图片是否需要拍摄时间、原图分辨率等其他信息，0 否、1 是，默认0
$needmedia = 56; // int | 视频是否需要展示时长信息，needmedia=1时，返回 duration 信息时间单位为秒 （s），转换为向上取整。0 否、1 是，默认0
$fsids = array('fsids_example'); // string[] | 文件id数组，数组中元素是uint64类型，数组大小上限是：100

try {
    $result = $apiInstance->xpanMultimediaFilemetas($dlink, $path, $thumb, $extra, $needmedia, $fsids);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanMultimediaFilemetas: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **dlink** | **int**| 是否需要下载地址，0为否，1为是，默认为0。获取到dlink后，参考下载文档进行下载操作 | |
| **path** | **string**| 查询共享目录或专属空间内文件时需要。共享目录格式： /uk-fsid 其中uk为共享目录创建者id， fsid对应共享目录的fsid 专属空间格式：/_pcs_.appdata/xpan/ | |
| **thumb** | **int**| 是否需要缩略图地址，0为否，1为是，默认为0 | |
| **extra** | **int**| 图片是否需要拍摄时间、原图分辨率等其他信息，0 否、1 是，默认0 | |
| **needmedia** | **int**| 视频是否需要展示时长信息，needmedia&#x3D;1时，返回 duration 信息时间单位为秒 （s），转换为向上取整。0 否、1 是，默认0 | |
| **fsids** | [**string[]**](../Model/string.md)| 文件id数组，数组中元素是uint64类型，数组大小上限是：100 | [optional] |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanMultimediaFilemetas200Response**](../Model/XpanMultimediaFilemetas200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanMultimediaListall()`

```php
xpanMultimediaListall($recursion, $order, $desc, $start, $limit, $ctime, $mtime, $web, $path): \Clainy\OpenxpanApiClient\Model\XpanMultimediaListall200Response
```

递归获取文件列表

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$recursion = 56; // int | 是否递归，0为否，1为是，默认为0
$order = 'order_example'; // string | 排序字段:time(修改时间)，name(文件名)，size(大小，目录无大小)，默认为文件类型
$desc = 'desc_example'; // string | 0为升序，1为降序，默认为0
$start = 56; // int | 查询起点，默认为0
$limit = 56; // int | 查询数目，默认为1000；如果设置start和limit参数，则建议最大设置为1000
$ctime = 56; // int | 文件上传时间，设置此参数，表示只返回上传时间大于ctime的文件
$mtime = 56; // int | 文件修改时间，设置此参数，表示只返回修改时间大于mtime的文件
$web = 56; // int | 默认为0， 为1时返回缩略图地址
$path = 'path_example'; // string | 目录名称绝对路径，必须/开头；路径包含中文时需要UrlEncode编码 ；给出的示例的路径是/测试目录的UrlEncode编码。

try {
    $result = $apiInstance->xpanMultimediaListall($recursion, $order, $desc, $start, $limit, $ctime, $mtime, $web, $path);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanMultimediaListall: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **recursion** | **int**| 是否递归，0为否，1为是，默认为0 | |
| **order** | **string**| 排序字段:time(修改时间)，name(文件名)，size(大小，目录无大小)，默认为文件类型 | |
| **desc** | **string**| 0为升序，1为降序，默认为0 | |
| **start** | **int**| 查询起点，默认为0 | |
| **limit** | **int**| 查询数目，默认为1000；如果设置start和limit参数，则建议最大设置为1000 | |
| **ctime** | **int**| 文件上传时间，设置此参数，表示只返回上传时间大于ctime的文件 | |
| **mtime** | **int**| 文件修改时间，设置此参数，表示只返回修改时间大于mtime的文件 | |
| **web** | **int**| 默认为0， 为1时返回缩略图地址 | |
| **path** | **string**| 目录名称绝对路径，必须/开头；路径包含中文时需要UrlEncode编码 ；给出的示例的路径是/测试目录的UrlEncode编码。 | [optional] |

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanMultimediaListall200Response**](../Model/XpanMultimediaListall200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `xpanNasUinfo()`

```php
xpanNasUinfo(): \Clainy\OpenxpanApiClient\Model\XpanNasUinfo200Response
```

获取用户信息

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyName
$config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKey('access_token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Clainy\OpenxpanApiClient\Configuration::getDefaultConfiguration()->setApiKeyPrefix('access_token', 'Bearer');


$apiInstance = new Clainy\OpenxpanApiClient\Api\DefaultApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->xpanNasUinfo();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->xpanNasUinfo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Clainy\OpenxpanApiClient\Model\XpanNasUinfo200Response**](../Model/XpanNasUinfo200Response.md)

### Authorization

[ApiKeyName](../../README.md#ApiKeyName)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
