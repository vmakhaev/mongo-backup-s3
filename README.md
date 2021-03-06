#mongo-backup-s3

A simple docker container to backup mongo to s3.  Easy to integrate with cron.

## Usage

To initiate a backup.

```
docker run --rm --link mongo:mongo -e AWS_ACCESS_KEY_ID=123 -e AWS_SECRET_ACCESS_KEY=123 -e S3_BUCKET=bucket -e S3_MONGO_PREFIX=mongo vmakhaev/mongo-backup-s3 backup
```

To list the backups on s3.

```
docker run --rm --link mongo:mongo -e AWS_ACCESS_KEY_ID=123 -e AWS_SECRET_ACCESS_KEY=123 -e S3_BUCKET=bucket -e S3_MONGO_PREFIX=mongo vmakhaev/mongo-backup-s3 list
```

To restore a given backup, where `[backup-file-name]` is the name of the backup file you would like to restore.

```
docker run --rm --link mongo:mongo -e AWS_ACCESS_KEY_ID=123 -e AWS_SECRET_ACCESS_KEY=123 -e S3_BUCKET=bucket -e S3_MONGO_PREFIX=mongo vmakhaev/mongo-backup-s3 restore [backup-file-name]
```
