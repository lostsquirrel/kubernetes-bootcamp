SHELL=/bin/bash

REGISTRY=registry.cn-hangzhou.aliyuncs.com
REGISTRY_NAMESPACE=lisong
PROJECT_NAME=kubernetes-bootcamp
VERSION=v1

VERSION_TAG=$(VERSION)

IMAGE=$(REGISTRY)/$(REGISTRY_NAMESPACE)/$(PROJECT_NAME)
VERSIONED_IMAGE=$(IMAGE):$(VERSION_TAG)

# 登陆registry
login:
	docker login registry.cn-hangzhou.aliyuncs.com

prepare:
	cp $(VERSION)/server.js .
# Push to registry. 推送到远程仓库
push:
	docker push $(VERSIONED_IMAGE)

pull:
	docker pull $(VERSIONED_IMAGE)

build:
	docker build --no-cache -t $(VERSIONED_IMAGE) .

test:
	docker run --rm  $(VERSIONED_IMAGE)
