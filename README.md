# Tensorflow Object Detection with Tensorflow 2

![duckies_test](https://github.com/patilabhi20/gesture-controlled-robotic-hand-by-using-CV/assets/157373320/f9f966e4-1bd5-48cf-8f1f-4beaad4bce70)



## Installation

You can install the TensorFlow Object Detection API either with Python Package Installer (pip) or [Docker](https://www.docker.com/), an open-source platform for deploying and managing containerized applications. 



### Docker Installation

```
# From the root of the git repository (inside the models directory)
docker build -f research/object_detection/dockerfiles/tf2/Dockerfile -t od .
docker run -it od
```

### Python Package Installation

```
cd models/research
# Compile protos.
protoc object_detection/protos/*.proto --python_out=.
# Install TensorFlow Object Detection API.
cp object_detection/packages/tf2/setup.py .
python -m pip install .
```


```python
import os
import sys
args = sys.argv
directory = args[1]
protoc_path = args[2]
for file in os.listdir(directory):
    if file.endswith(".proto"):
        os.system(protoc_path+" "+directory+"/"+file+" --python_out=.")
```

```
python use_protobuf.py <path to directory> <path to protoc file>
```

To test the installation run:

```
# Test the installation.
python object_detection/builders/model_builder_tf2_test.py
```




