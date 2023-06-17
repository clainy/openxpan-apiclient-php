# # XpanFileCreate200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**errno** | **int** | 错误码 |
**fs_id** | **int** | 文件在云端的唯一标识ID |
**md5** | **string** | 文件的MD5，只有提交文件时才返回，提交目录时没有该值 |
**server_filename** | **string** | 文件名 |
**category** | **int** | 创建文件: 分类类型, 1 视频 2 音频 3 图片 4 文档 5 应用 6 其他 7 种子; 创建文件夹: 分类类型, 6 文件夹 |
**path** | **string** | 上传后使用的文件绝对路径 |
**size** | **int** | 文件大小，单位B |
**ctime** | **int** | 文件创建时间 |
**mtime** | **int** | 文件修改时间 |
**isdir** | **int** | 是否目录，0 文件、1 目录 |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
