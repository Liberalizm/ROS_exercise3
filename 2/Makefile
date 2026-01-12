CUR_DIR = $(shell pwd)

build:
	docker build -t "$$USER-example-image" --progress=plain .
	docker run --rm -v ./:/workspace --entrypoint=colcon "$$USER-example-image" build

run:
	docker run --rm -it --network=host --privileged -v /dev/shm:/dev/shm -v ./:/workspace "$$USER-example-image"

.PHONY: run build