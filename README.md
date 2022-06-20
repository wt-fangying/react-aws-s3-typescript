# 源码来源于 react-aws-s3-typescript

```typescript
const config = {
  bucketName: ServerConfig.uploadBucketName,
  region: ServerConfig.uploadRegion,
  accessKeyId: ServerConfig.uploadAccessKeyId,
  secretAccessKey: ServerConfig.uploadSecretAccessKey,
};
const ReactS3Client = new S3(config);
```

## 修改添加了取消上传
```typescript
// 取消上传
ReactS3Client.channelUpload()
```

## 增加了进度条功能

```typescript
const onProgress = (progressEvent: { loaded: number; total: number }) => {
    const percentCompleted = Math.round(
      (progressEvent.loaded * 100) / progressEvent.total,
    );
  };

// 上传
ReactS3Client.uploadFile(file, onProgress)
```
