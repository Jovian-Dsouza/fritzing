# fritzing
Scripts to Install Fritzing for free using docker

## Setup 
```
mkdir ~/fritzing && cd ~/fritzing
git clone https://github.com/fritzing/fritzing-parts
```


## Run the fritzing docker instance
```bash
sudo service docker start
xhost +local:docker  #give docker access to the xserver
docker run -it --rm -e DISPLAY=$DISPLAY \
            -v ~/fritzing/saved:/home/conan/saved \
            -v ~/fritzing/fritzing-parts:/home/conan/fritzing-parts \
            -v /tmp/.X11-unix:/tmp/.X11-unix \
            salwaelk/fritzing-bionic:latest > /dev/null
```
