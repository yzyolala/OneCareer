```java
{
    "mongodbConnectURI":"mongodb+srv://admin:admin@cluster0.luinmsr.mongodb.net/?retryWrites=true&w=majority", // MongoDB的连接URI，用于连接到MongoDB数据库服务
    "jwtSecret":"meetfoodSecretToken", // 用于JWT(JSON Web Token)签名的密钥
    "jwtExpireTime":360000, // JWT的过期时间，单位是毫秒
    "CognitoRegion": "us-east-1", // AWS Cognito服务的地区
    "CognitoToCUserPoolId": "us-east-1_NVPBjMKzp", // AWS Cognito的用户池ID
    "CognitoTokenUse": "access", // AWS Cognito使用的令牌类型
    "CognitoTokenExpiration": 8640000, // AWS Cognito令牌的过期时间，单位是毫秒

    "S3AccessKeyID": "", // AWS S3的访问密钥ID
    "S3SecretAccessKey": "xxxxxxx", // AWS S3的秘密访问密钥
    "S3ProfilePhotoBucketName": "xxxxxxx", // 用于存储个人资料照片的S3 bucket名
    "S3CoverImageBucketName": "xxxxxxx", // 用于存储封面图片的S3 bucket名
    "S3VideoBucketName": "xxxxxxx", // 用于存储视频的S3 bucket名
    "S3VideoUrlPrefix": "xxxxxxx", // 视频在S3上的URL前缀
    "S3ProfilePhotoUrlPrefix": "xxxxxxx", // 个人资料照片在S3上的URL前缀
    "S3CoverImageUrlPrefix": "xxxxxxx" // 封面图片在S3上的URL前缀
}
```
