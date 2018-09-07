repo = hub.tech-pi.com/env
name = slurm-client
VERSION := $(shell cat version | tr -d '\n')
image :
	sudo cp ../munge.key .
	sudo docker build -t $(repo)/$(name):$(VERSION) -t $(repo)/$(name):latest .
push :
	sudo docker push $(repo)/$(name):latest
pull :
	sudo docker pull $(repo)/$(name):latest
run :
	sudo docker run -h $(name) -v $(SPACK_DEVELOP_ROOT):/opt/spack -v /home/qinglong/node3share/dxcluster/src/docker/slurm/config:/etc/slurm-llnl/  -it --rm $(repo)/$(name)

