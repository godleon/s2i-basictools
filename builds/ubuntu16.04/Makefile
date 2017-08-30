IMAGE_NAME = s2i-basictools
TAG_NAME = ubuntu16.04

.PHONY: build
build:
	docker build -t $(IMAGE_NAME):$(TAG_NAME) .

.PHONY: test
test:
	docker build -t $(IMAGE_NAME):$(TAG_NAME) .
	IMAGE_NAME=$(IMAGE_NAME) TAG_NAME=$(TAG_NAME) test/run.sh