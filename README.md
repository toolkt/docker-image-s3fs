## Mount aws s3 folder to a container and export as a volume

### Usage

#### Run container to mount s3 folder

    docker run -d --name aws-s3-mount-some-bucket-folder innovativetravel/aws-s3-mount -e AWS_ACCESS_KEY_ID=key -e AWS_SECRET_ACCESS_KEY=secret -e S3_PATH=some-bucket/folder

Environment variables to configure

* AWS_ACCESS_KEY_ID

* AWS_SECRET_ACCESS_KEY

* AWS_DEFAULT_REGION

* S3_PATH

See https://github.com/danilop/yas3fs for more options

Volumes exported

* /mnt


##License

This software is licensed under the [MIT license](http://en.wikipedia.org/wiki/MIT_License).

© 2016 Innovative Travel Ltd
