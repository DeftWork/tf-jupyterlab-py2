# DEPRECATED - BE AWARE

DEPRECATION: Python 2.7 will reach the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 won't be maintained after that date. A future version of pip will drop support for Python 2.7.

A [Docker](http://docker.com) file to build images for AMD & ARM devices over a base image based with a minimal installation of [Tensorflow](https://www.tensorflow.org/) an open source software library for numerical computation using data flow graphs.
Over this base will be installed [JupyterLab](https://github.com/jupyterlab/jupyterlab) an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text. Computational Narratives as the Engine of Collaborative Data Science. All this under Python 2 language. [Python 3 version here](https://github.com/DeftWork/tf-jupyterlab).

> Be aware! You should read carefully the usage documentation of every tool!

## Details

- [GitHub](https://github.com/DeftWork/tf-jupyterlab-py2)
- [Deft.Work my personal blog](http://deft.work/tensorflow_for_raspberry)

| Docker Hub | Docker Pulls | Docker Stars | Docker Build | Size/Layers |
| --- | --- | --- | --- | --- |
| [tf-jupyterlab-py2](https://hub.docker.com/r/elswork/tf-jupyterlab-py2 "elswork/tf-jupyterlab-py2 on Docker Hub") | [![](https://img.shields.io/docker/pulls/elswork/tf-jupyterlab-py2.svg)](https://hub.docker.com/r/elswork/tf-jupyterlab-py2 "tf-jupyterlab-py2 on Docker Hub") | [![](https://img.shields.io/docker/stars/elswork/tf-jupyterlab-py2.svg)](https://hub.docker.com/r/elswork/tf-jupyterlab-py2 "tf-jupyterlab-py2 on Docker Hub") | [![](https://img.shields.io/docker/build/elswork/tf-jupyterlab-py2.svg)](https://hub.docker.com/r/elswork/tf-jupyterlab-py2 "tf-jupyterlab-py2 on Docker Hub") | [![](https://images.microbadger.com/badges/image/elswork/tf-jupyterlab-py2.svg)](https://microbadger.com/images/elswork/tf-jupyterlab-py2 "tf-jupyterlab-py2 on microbadger.com") |

This image is the base image for a set of images [Data Science Docker Stacks](https://goo.gl/qvx7Vv)

## Build Instructions

Build Python2 flavour for amd64 or arm32v7 architecture (thanks to its [Multi-Arch](https://blog.docker.com/2017/11/multi-arch-all-the-things/) base image)

```sh
docker build -t elswork/tf-jupyterlab-py2:latest .
```

## My Real Usage Example

In order everyone could take full advantages of the usage of this docker container, I'll describe my own real usage setup.

```sh
docker run -d -p 8888:8888 elswork/tf-jupyterlab-py2:latest
```

A more complex sample:

```sh
docker run -d -p 8888:8888 -p 0.0.0.0:6006:6006 \
 --restart=unless-stopped elswork/tf-jupyterlab-py2:latest
```

Point your browser to `http://localhost:8888`

First time you open it, you should provide a Token to log on you cand find it with this command:

```sh
docker logs container_name
```

With the second example you can run TensorBoard executing this command in the container:

```sh
tensorboard --logdir=path/to/log-directory --host=0.0.0.0
```

And pointing your browser to `http://localhost:6006`