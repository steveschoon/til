# AWS CLI Commands

## S3

#### Copy all files from AWS bucket to local
```
aws cp s3://foo/bar/ ./ --recursive
```
#### Copy just EXEs from AWS bucket to local
```
aws cp s3://foo/bar/ ./ --recursive --exclude "*" --include "*.exe"
```

