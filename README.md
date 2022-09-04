# stable_diffusion.openvino-docker

## Introduction

This is a Dockerfile to use stable_diffusion.openvino[^1] in Docker container.

## Requirements

- Intel CPU
- Docker

## Build Docker image

```shell
docker build --build-arg UID=$(id -u) --build-arg GID=$(id -g) -t stable_diffusion:openvino .
```

## Launch Docker container

```shell
docker run -it --rm --device /dev/dri:/dev/dri -v $HOME:$HOME stable_diffusion:openvino bash
```

## Example

```shell
python stable_diffusion.py --prompt "Street-art painting of Emilia Clarke in style of Banksy, photorealism"
```

## Example via streamlit

When docker run, map port 8501 for streamlit.

```shell
docker run -it --rm -p 8501:8501 stable_diffusion:openvino bash
```

```shell
streamlit run demo_web.py 
```

access http://(Your IP Address):8501

[^1]: stable_diffusion.openvino <https://github.com/bes-dev/stable_diffusion.openvino>  

