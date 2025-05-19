_This is NOT an original piece of work, just a snap of MinIO_

MinIO is a High Performance Object Storage released under GNU Affero General Public License v3.0. It is API compatible with Amazon S3 cloud storage service. Use MinIO to build high performance infrastructure for machine learning, analytics and application data workloads.

Read the doc at https://min.io/docs/minio/linux/index.html

### Connect the interfaces
```
sudo snap connect minio-gael:mount-observe
sudo snap connect minio-gael:block-devices
sudo snap connect minio-gael:system-observe
sudo snap connect minio-gael:network-control
```

### Configure MinIO daemon (Example)
```
sudo mkdir -p /var/snap/minio-gael/common/data

sudo vi /var/snap/minio-gael/current/minio-daemon.options
```

```
--anonymous server /var/snap/minio-gael/common/data
```

```
sudo snap start --enable minio-gael.minio-daemon
``` 

### Run MinIO server (Example)

```
sudo minio-gael.minio server /var/snap/minio-gael/common/data/

USAGE:
  minio [FLAGS] COMMAND [ARGS...]

COMMANDS:
  server  start object storage server
  
FLAGS:
  --certs-dir value, -S value  path to certs directory (default: "/root/snap/minio-gael/x1/.minio/certs")
  --quiet                      disable startup and info messages
  --anonymous                  hide sensitive information from logging
  --json                       output logs in JSON format
  --help, -h                   show help
  --version, -v                print the version
```

### Run MinIO client (Example)

```
sudo minio-gael.mc [FLAGS] COMMAND [COMMAND FLAGS | -h] [ARGUMENTS...]
```

