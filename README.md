# docker-fluentd-s3

this command will route all containers outputs to s3 bucket:

	docker run --name logger -d -e AWS_KEY=key \
		-e AWS_SECRET=secret \
		-e S3_REGION=us-east-1 \
		-e S3_BUCKET=mybucket \
		-e S3_PATH=logs/ \
		-v /var/lib/docker/containers:/var/lib/docker/containers \
		-v /var/log/docker:/var/log/docker \
		tmuskal/fluentd-s3
