# Top section copied from http://clarkgrubb.com/makefile-style-guide
MAKEFLAGS += --warn-undefined-variables
SHELL := bash
.SHELLFLAGS := -o errexit -o nounset -o pipefail -c
.SUFFIXES:

IMAGE_NAME := mbuzi/mbuzi-cicd:v0.0.1

image:
	docker build -t ${IMAGE_NAME} .

push: image
	docker login -u ${DOCKERHUB_USERNAME} -p ${DOCKERHUB_PASS}
	docker push ${IMAGE_NAME}

# SECTION: CIRCLECI
circleci-local:
	circleci config process .circleci/config.yml > .circleci/process.yml
	circleci local execute --config .circleci/process.yml
