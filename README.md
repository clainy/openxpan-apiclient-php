# openxpan-apiclient-php

API for accessing XPan NAS data


## Installation & Usage

### Requirements

PHP 7.4 and later.
Should also work with PHP 8.0.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/clainy/openxpan-apiclient-php.git"
    }
  ],
  "require": {
    "clainy/openxpan-apiclient-php": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/openxpan-apiclient-php/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

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
    new GuzzleHttpClient(["defaults" => ["verify" => false]]),
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

## API Endpoints

All URIs are relative to *https://pan.baidu.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*DefaultApi* | [**apiCategoryinfo**](docs/Api/DefaultApi.md#apicategoryinfo) | **GET** /api/categoryinfo | 获取分类文件总个数
*DefaultApi* | [**apiQuota**](docs/Api/DefaultApi.md#apiquota) | **GET** /api/quota | 获取网盘容量信息
*DefaultApi* | [**pcsSuperfile2Upload**](docs/Api/DefaultApi.md#pcssuperfile2upload) | **POST** /rest/2.0/pcs/superfile2?method=upload | 分片上传
*DefaultApi* | [**xpanFileBtlist**](docs/Api/DefaultApi.md#xpanfilebtlist) | **GET** /rest/2.0/xpan/file?method=btlist | 获取bt列表
*DefaultApi* | [**xpanFileCreate**](docs/Api/DefaultApi.md#xpanfilecreate) | **POST** /rest/2.0/xpan/file?method=create | 创建文件, 创建文件夹
*DefaultApi* | [**xpanFileDoclist**](docs/Api/DefaultApi.md#xpanfiledoclist) | **GET** /rest/2.0/xpan/file?method=doclist | 获取文档列表
*DefaultApi* | [**xpanFileFilemanager**](docs/Api/DefaultApi.md#xpanfilefilemanager) | **POST** /rest/2.0/xpan/file?method=filemanager | 管理文件
*DefaultApi* | [**xpanFileImagelist**](docs/Api/DefaultApi.md#xpanfileimagelist) | **GET** /rest/2.0/xpan/file?method=imagelist | 获取图片列表
*DefaultApi* | [**xpanFileList**](docs/Api/DefaultApi.md#xpanfilelist) | **GET** /rest/2.0/xpan/file?method=list | 获取文件列表
*DefaultApi* | [**xpanFilePrecreate**](docs/Api/DefaultApi.md#xpanfileprecreate) | **POST** /rest/2.0/xpan/file?method=precreate | 预上传
*DefaultApi* | [**xpanFileSearch**](docs/Api/DefaultApi.md#xpanfilesearch) | **GET** /rest/2.0/xpan/file?method=search | 搜索文件
*DefaultApi* | [**xpanFileVideolist**](docs/Api/DefaultApi.md#xpanfilevideolist) | **GET** /rest/2.0/xpan/file?method=videolist | 获取视频列表
*DefaultApi* | [**xpanMultimediaCategorylist**](docs/Api/DefaultApi.md#xpanmultimediacategorylist) | **GET** /rest/2.0/xpan/multimedia?method=categorylist | 获取分类文件列表
*DefaultApi* | [**xpanMultimediaFilemetas**](docs/Api/DefaultApi.md#xpanmultimediafilemetas) | **GET** /rest/2.0/xpan/multimedia?method=filemetas | 查询文件信息
*DefaultApi* | [**xpanMultimediaListall**](docs/Api/DefaultApi.md#xpanmultimedialistall) | **GET** /rest/2.0/xpan/multimedia?method=listall | 递归获取文件列表
*DefaultApi* | [**xpanNasUinfo**](docs/Api/DefaultApi.md#xpannasuinfo) | **GET** /rest/2.0/xpan/nas?method=uinfo | 获取用户信息

## Models

- [ApiCategoryinfo200Response](docs/Model/ApiCategoryinfo200Response.md)
- [ApiQuota200Response](docs/Model/ApiQuota200Response.md)
- [PcsSuperfile2Upload200Response](docs/Model/PcsSuperfile2Upload200Response.md)
- [PostPcsSuperfile2Upload](docs/Model/PostPcsSuperfile2Upload.md)
- [PostXpanFileCreate](docs/Model/PostXpanFileCreate.md)
- [PostXpanFileFilemanager](docs/Model/PostXpanFileFilemanager.md)
- [PostXpanFilePrecreate](docs/Model/PostXpanFilePrecreate.md)
- [ResponseInfo](docs/Model/ResponseInfo.md)
- [ResponseList](docs/Model/ResponseList.md)
- [XpanFileCreate200Response](docs/Model/XpanFileCreate200Response.md)
- [XpanFileDoclist200Response](docs/Model/XpanFileDoclist200Response.md)
- [XpanFileFilemanager200Response](docs/Model/XpanFileFilemanager200Response.md)
- [XpanFileList200Response](docs/Model/XpanFileList200Response.md)
- [XpanFilePrecreate200Response](docs/Model/XpanFilePrecreate200Response.md)
- [XpanFileSearch200Response](docs/Model/XpanFileSearch200Response.md)
- [XpanMultimediaCategorylist200Response](docs/Model/XpanMultimediaCategorylist200Response.md)
- [XpanMultimediaFilemetas200Response](docs/Model/XpanMultimediaFilemetas200Response.md)
- [XpanMultimediaListall200Response](docs/Model/XpanMultimediaListall200Response.md)
- [XpanNasUinfo200Response](docs/Model/XpanNasUinfo200Response.md)

## Authorization

Authentication schemes defined for the API:
### ApiKeyName

- **Type**: API key
- **API key parameter name**: access_token
- **Location**: URL query string


## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author



## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.0.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
