# S3Bubble Player

```
npm install @s3bubble/player
```


```js

```

# API

## Available Params

| Params              | Description                                                                 |
| ------------------- | --------------------------------------------------------------------------- |
| localFolderPath     | The path to the folder on your computer you want to upload                  |
| s3UploadBucket      | The AWS S3 bucket name you want to upload to                                |
| s3UploadFolder      | The AWS S3 folder name you want to upload to                                |
| chunkSize           | The size to split the files into manageable chunks to upload                |
| removeUploadedFiles | If set when a batch of files have been uploaded they will be delete locally |
| filterExtensions    | Only upload files with specific extensions accepts array ['mp3','mp4']      |
| accessKeyId         | Your AWS IAM access id                                                      |
| secretAccessKey     | Your AWS IAM secret access key                                              |

## Available Events

| Events   | Description                                                |
| -------- | ---------------------------------------------------------- |
| progress | Lists progress, totalProgress, chunkedIndex, chunkedLength |
| finished | When all files have been uploaded                          |
| files    | Returns the batch of uploaded files                        |
| error    | Lists any errors                                           |

## Things to add

-   Set ACL's to public or private
-   Check if file exists first before uploading
-   Add retry
