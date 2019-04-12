[![Build Status](https://travis-ci.org/wharton/S3WebCache.svg?branch=master)](https://travis-ci.org/wharton/S3WebCache)

# S3 Web Cache
This is a simple package for archiving web pages (HTML) to S3. It acts as a cache serving the S3 version of the page if it exists. If not it writes a version to s3.

## Quickstart

### Install

`pip install s3webcache`

### Usage

```
from s3webcache import S3WebCache

s3wc = S3WebCache(
    bucket_name=<BUCKET>,
    aws_access_key_id=<AWS_ACCESS_KEY_ID>,
    aws_secret_key=<AWS_SECRET_ACCESS_KEY>,
    aws_default_region=<AWS_DEFAULT_REGION>)

request = s3wc.get("https://en.wikipedia.org/wiki/Whole_Earth_Catalog")

if request.success:
    html = request.message
```
