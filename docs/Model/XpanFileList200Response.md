# # XpanFileList200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**fs_id** | **int** | 文件在云端的唯一标识ID |
**path** | **string** | 文件的绝对路径 |
**server_filename** | **string** | 文件名称 |
**size** | **int** | 文件大小，单位B |
**server_mtime** | **int** | 文件在服务器修改时间 |
**server_ctime** | **int** | 文件在服务器创建时间 |
**local_mtime** | **int** | 文件在客户端修改时间 |
**local_ctime** | **int** | 文件在客户端创建时间 |
**isdir** | **int** | 是否为目录，0 文件、1 目录 |
**category** | **int** | 文件类型，1 视频、2 音频、3 图片、4 文档、5 应用、6 其他、7 种子 |
**md5** | **string** | 云端哈希（非文件真实MD5），只有是文件类型时，该字段才存在 |
**dir_empty** | **int** | 该目录是否存在子目录，只有请求参数web&#x3D;1且该条目为目录时，该字段才存在， 0为存在， 1为不存在 |
**thumbs** | **string[]** | 只有请求参数web&#x3D;1且该条目分类为图片时，该字段才存在，包含三个尺寸的缩略图URL |
**info** | [**\Clainy\OpenxpanApiClient\Model\ResponseInfo[]**](ResponseInfo.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
