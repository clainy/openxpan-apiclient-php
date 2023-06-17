# # ResponseList

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**category** | **int** | 文件类型，含义如下：1 视频， 2 音乐，3 图片，4 文档，5 应用，6 其他，7 种子 | [optional]
**dlink** | **string** | 文件下载地址，参考下载文档进行下载操作 | [optional]
**file_name** | **string** | 文件名 | [optional]
**isdir** | **int** | 是否是目录，为1表示目录，为0表示非目录 | [optional]
**server_ctime** | **int** | 文件的服务器创建Unix时间戳，单位秒 | [optional]
**server_mtime** | **int** | 文件的服务器修改Unix时间戳，单位秒 | [optional]
**size** | **int** | 文件大小，单位字节 | [optional]
**thumbs** | **string[]** | 缩略图地址 | [optional]
**height** | **int** | 图片高度 | [optional]
**width** | **int** | 图片宽度 | [optional]
**date_taken** | **int** | 图片拍摄时间 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
