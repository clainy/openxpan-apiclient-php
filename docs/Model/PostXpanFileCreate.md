# # PostXpanFileCreate

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**path** | **string** | 创建文件: 上传后使用的文件绝对路径，需要urlencode，需要与预上传precreate接口中的path保持一致; 创建文件夹: 创建文件夹的绝对路径，需要urlencode | [optional]
**size** | **string** | 文件或目录的大小，必须要和文件真实大小保持一致，需要与预上传precreate接口中的size保持一致 | [optional]
**isdir** | **string** | 创建文件: 是否目录，0 文件、1 目录，需要与预上传precreate接口中的isdir保持一致; 创建文件夹: 本接口固定为1 | [optional]
**block_list** | **string[]** | 文件各分片md5数组的json串需要与预上传precreate接口中的block_list保持一致，同时对应分片上传superfile2接口返回的md5，且要按照序号顺序排列，组成md5数组的json串。 | [optional]
**uploadid** | **string** | 预上传precreate接口下发的uploadid | [optional]
**rtype** | **int** | 文件命名策略，默认00 为不重命名，返回冲突1 为只要path冲突即重命名2 为path冲突且block_list不同才重命名3 为覆盖，需要与预上传precreate接口中的rtype保持一致 | [optional]
**local_ctime** | **int** | 客户端创建时间(精确到秒)，默认为当前时间戳 | [optional]
**local_mtime** | **int** | 客户端修改时间(精确到秒)，默认为当前时间戳 | [optional]
**zip_quality** | **int** | 图片压缩程度，有效值50、70、100 | [optional]
**zip_sign** | **int** | 未压缩原始图片文件真实md5 | [optional]
**is_revision** | **int** | 是否需要多版本支持1为支持，0为不支持， 默认为0 (带此参数会忽略重命名策略) | [optional]
**mode** | **int** | 上传方式1 手动、2 批量上传、3 文件自动备份4 相册自动备份、5 视频自动备份 | [optional]
**exif_info** | **string** | json字符串，orientation、width、height、recovery为必传字段，其他字段如果没有可以不传 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
