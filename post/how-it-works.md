+++
title= "How It Works"
date= 2019-10-03T23:13:07+02:00
tags= ["how"]
description= "s3mon -c config.yml"
+++

# In a nutshell

**s3mon** will list and search for files of a certain pattern
on a list of defined buckets that are not older than a defined
period. These options are defined in a `config.yml` file
([YAML formated](https://en.wikipedia.org/wiki/YAML))


# The config file

Example of a configuration file:

```yaml
---
s3mon:
  endpoint: s3.provider
  region: <aws-region>
  access_key: ACCESS_KEY_ID
  secret_key: SECRET_ACCESS_KEY
  buckets:
    bucket_A:
      - prefix: starts_with_foo
        age: 86400
        size: 30720
    bucket_B:
      - prefix: file
        age: 43200
        size: 1024
      - prefix: exact_file_name
        age: 43200
```

If your **S3** provider is **AWS** you can omit the `endpoint` and only specify
a `region`, for example:

```yaml
---
s3mon:
  region: us-east-1
  access_key: ACCESS_KEY_ID
  secret_key: SECRET_ACCESS_KEY
  buckets:
    bucket_name:
      - prefix: starts_with_foo
        age: 86400
        size: 30720
```

The `access_key` and `secret_key` can be omitted if the environment vars
`AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` are set, example:

```yaml
---
s3mon:
  region: us-east-1
  buckets:
    bucket_name:
      - prefix: starts_with_foo
        age: 86400
        size: 30720
```
