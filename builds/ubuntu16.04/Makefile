IMAGE_NAME = s2i-basictools:16.04

.PHONY: build
build:
	docker build -t $(IMAGE_NAME) .

.PHONY: test
test:
	docker build -t $(IMAGE_NAME) .
	IMAGE_NAME=$(IMAGE_NAME) test/run.sh