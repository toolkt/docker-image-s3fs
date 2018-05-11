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


#### Build Docker

#1. Get the files from Github
```sh
git clone git@github.com:toolkt/docker-image-s3fs.git
```

#2 Build the image 
```sh
cd docker-image-s3fs/
docker build -t toolkt/s3fs .
```

#3. Run the container
```sh
docker run -d --name s3fs toolkt/s3fs -e AWS_ACCESS_KEY_ID=key -e AWS_SECRET_ACCESS_KEY=secret -e S3_PATH=some-bucket/folder
```

#4, Push the image to docker hub
```sh
#Commit the running container to the image and then to Docker
docker login
docker commit s3fs toolkt/s3fs
docker push toolkt/s3fs

```




##License

This software is licensed under the [MIT license](http://en.wikipedia.org/wiki/MIT_License).

© 2016 Innovative Travel Ltd
