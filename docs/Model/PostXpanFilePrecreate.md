# # PostXpanFilePrecreate

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**path** | **string** | 上传后使用的文件绝对路径，需要urlencode | [optional]
**size** | **int** | 文件和目录两种情况：上传文件时，表示文件的大小，单位B；上传目录时，表示目录的大小，目录的话大小默认为0 | [optional]
**isdir** | **int** | 是否为目录，0 文件，1 目录 | [optional]
**block_list** | **string[]** | 文件各分片MD5数组的json串。block_list的含义如下，如果上传的文件小于4MB，其md5值（32位小写）即为block_list字符串数组的唯一元素；如果上传的文件大于4MB，需要将上传的文件按照4MB大小在本地切分成分片，不足4MB的分片自动成为最后一个分片，所有分片的md5值（32位小写）组成的字符串数组即为block_list。 | [optional]
**autoinit** | **int** | 固定值1 | [optional]
**rtype** | **int** | 文件命名策略。1 表示当path冲突时，进行重命名2 表示当path冲突且block_list不同时，进行重命名3 当云端存在同名文件时，对该文件进行覆盖 | [optional]
**uploadid** | **string** | 上传ID | [optional]
**content_md5** | **string** | 文件MD5，32位小写 | [optional]
**slice_md5** | **string** | 文件校验段的MD5，32位小写，校验段对应文件前256KB | [optional]
**local_ctime** | **string** | 客户端创建时间， 默认为当前时间戳 | [optional]
**local_mtime** | **string** | 客户端修改时间，默认为当前时间戳 | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
