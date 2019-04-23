# Udacity Bike Sharing Prediction Project

This is my solution for the Bike Sharing project for [Udacity's Deep Learning Nanodegree](https://www.udacity.com/course/deep-learning-nanodegree--nd101), which is a general overview of nerural networks including CNNs, RNNs, and GANs. This Nanodegree originally used NumPy, Keras, and TensorFlow, though the class has since been updated to use PyTorch instead of Keras and TensorFlow.

In this specific project, we were tasked with creating a basic neural network with NumPy to predict daily bike sharing rentals. The network itself is implemented in my_answers.py.

## Requirements

- [Python 3.6](https://www.python.org/downloads/release/python-367/) (Any Python 3 interpreter should work here, but 3.6 was used to run this project)
- (Optional for Docker support) [Docker](https://docs.docker.com/install/), (For GPU support) [nvidia-docker](https://github.com/NVIDIA/nvidia-docker)
- See requirements.txt for a list of other required packages.


# Run the Project
## Option One: The Easy Way

I have created Docker images which contain all of the projects completed for the Deep Learning Nanodegree. They are a bit large and as a result may take some time to download, but it will likely be less aggravating than making sure all the package dependencies are met on your native machine. To use these images, all you need to do is pull from jmontag/udacity_dl with the appropriate CPU or GPU tag. For the CPU image the commands are:
```sh
$ sudo docker pull jmontag/udacity_dl:cpu
$ sudo docker run -it --rm -p 8888:8888 jmontag/udacity_dl:cpu
```

For GPU:
```sh
$ sudo docker pull jmontag/udacity_dl:gpu
$ sudo docker run --runtime=nvidia -it --rm -p 8888:8888 jmontag/udacity_dl:gpu
```
**Note 1: if you are using nvidia-docker v1, you must use the `nvidia-docker run ...` alias and not `docker run --runtime=nvidia ...`**

**Note 2: I have had issues getting the GPU to work for some of the projects with RTX 20XX cards due to the fact that TensorFlow 1.12 requires CUDA 9.0. Your mileage may vary.**

This will start a [Jupyter Notebook](https://jupyter.org/) server on localhost at port 8888. You can then access the projects by copying the on screen link into your web browser: `http://127.0.0.1:8888/?token=...` and using the on screen GUI to run the Jupyter Notebook `.ipynb` files.

**Note 3: if you are running the GPU version, you may need to kill the current project's kernel before moving on to the next project. You can shut down the current notebook's kernel by going to the Kernel tab and selecting Shutdown. You can see all running kernels in the Running tab of the index page.**


## Option Two: Manual Install

It is recommended to use a virtual environment like [Virtualenv](https://virtualenv.pypa.io/en/stable/):
```sh
$ git clone https://github.com/jmontag43/udacity_bike_prediction.git
$ sudo pip install virtualenv
$ virtualenv -p python3.6 myenv		# Make sure you pass in your python 3.6 interpreter with -p
$ source myenv/bin/activate
(myenv) $ cd udacity_bike_prediction
(myenv) $ pip install -r requirements.txt
(myenv) $ jupyter notebook
```
**Note 1: Some shells (e.g. fish) require a different source command. In the fish example: `. myenv/bin/activate.fish`**

**Note 2: I have had issues getting the GPU to work for some of the projects with RTX 20XX cards due to the fact that pre-built TensorFlow 1.12 requires CUDA 9.0 which is incompatible with RTX 20XX.**

This will start a [Jupyter Notebook](https://jupyter.org/) server on localhost at port 8888. You can then access the projects by copying the on screen link into your web browser: `http://127.0.0.1:8888/?token=...` and using the on screen GUI to run the Jupyter Notebook `.ipynb` files.

When you are done, you can kill the jupyter server and run this command to deactivate your virtualenv:
```sh
(myenv) $ deactivate
```

