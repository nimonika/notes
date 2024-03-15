# S3 commands for downloading AIMS quads
```
export AWS_ACCESS_KEY_ID=xxxxx
export AWS_SECRET_ACCESS_KEY=xxxx

export AWS_ROLE_ARN=arn:aws:iam::626425755262:role/DSP2BucketAccessRole

eval $(aws sts assume-role --role-arn $AWS_ROLE_ARN --role-session-name s3 | jq -r '.Credentials | "export AWS_ACCESS_KEY_ID=\(.AccessKeyId)\nexport AWS_SECRET_ACCESS_KEY=\(.SecretAccessKey)\nexport AWS_SESSION_TOKEN=\(.SessionToken)\n"')

aws s3 ls defra-aims-backups
```