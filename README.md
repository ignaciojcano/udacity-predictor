[![CircleCI](https://circleci.com/gh/ignaciojcano/udacity-predictor/tree/master.svg?style=svg)](https://circleci.com/gh/ignaciojcano/udacity-predictor/tree/master)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

## Setup the Environment

* Create a virtualenv and activate it
```sh
python3 -m venv venv
. venv/bin/activate
```
* Run `make install` to install the necessary python dependencies
* Install hadolint https://github.com/hadolint/hadolint#install

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Make a prediction

A script is provided to make a test prediction, after the app is running, run `./make_prediction.sh`. This will do a get request to the app running on port 8000 (docker and kubernetes script set up this port by default)

### Uploading a new docker image

To upload a new image you can execute `./update_docker.sh`, the script will tag the latest built image as latest and upload it to docker hub. You can also specify a tag `./update_docker.sh 2.0` this will tag the image with the specified version and upload it to docker hub.
