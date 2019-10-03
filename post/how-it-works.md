+++
title= "How It Works"
date= 2019-10-03T23:13:07+02:00
tags= ["how"]
description= "s3mon -c config.yml"
+++

# In a nutshell

**s3mon** will list and search for files of a certain pattern on a list of
defifned buckets that are not older than a defined period. These options are defined in a `config.yml` file ([YAML formated](https://en.wikipedia.org/wiki/YAML))


# The config file (prototype)

Example of a config file:

```yaml
---
s3mon:
  endpoint: s3.provider
  access_key: ACCESS_KEY_ID
  secret_key: SECRET_ACCESS_KEY
  buckets:
    bucket_A:
      - file: starts_with_foo
        age: 86400
        size: 30720
    bucket_B:
      - file: file
        age: 43200
        size: 1024
      - file: exact_file_name
        age: 43200
```
