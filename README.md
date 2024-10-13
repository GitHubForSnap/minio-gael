
sudo mkdir -p /var/snap/minio-gael/common/data

sudo snap connect minio-gael:mount-observe

sudo minio-gael.minio server /var/snap/minio-gael/common/data/

