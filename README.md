# Multiclass-Classification-XGBoost

This is Dockerized ML multiclass classifier XGBoost model. It was created using the template from https://github.com/readytensor/rt-datasets-fars which provided a simple-to-adapt template for creating a dockerized multiclass classifier model implementation involving Jupyter Notebooks.

## Project Structure

The following is the directory structure of the project:

- **`model_inputs_outputs/`**: This directory contains files that are either inputs to, or outputs from, the model. When running the model locally (i.e. without using docker), this directory is used for model inputs and outputs. This directory is further divided into:
  - **`/inputs/`**: This directory contains all the input files for this project, including the `data` and `schema` files. The `data` is further divided into `testing` and `training` subsets.
  - **`/model/artifacts/`**: This directory is used to store the model artifacts, such as trained models and their parameters.
  - **`/outputs/`**: The outputs directory contains sub-directories for error logs, and hyperparameter tuning outputs, and prediction results.
- **`requirements/`**: This directory contains the requirements files. We have multiple requirements files for different purposes:
  - `requirements.txt` for the main code in the `src` directory
- **`src/`**: This directory holds the source code for the project. It is further divided into various subdirectories:
  - **`train.ipynb`**: This script is used to train the model. It loads the data, preprocesses it, trains the model, and saves the artifacts in the path `./model_inputs_outputs/model/artifacts/`.
  - **`predict.ipynb`**: This script is used to run batch predictions using the trained model. It loads the artifacts and creates and saves the predictions in a file called `predictions.csv` in the path `./model_inputs_outputs/outputs/predictions/`.
- **`.gitignore`**: This file specifies the files and folders that should be ignored by Git.
- **`Dockerfile`**: This file is used to build the Docker image for the application.
- **`entry_point.sh`**: This file is used as the entry point for the Docker container. It is used to run the application. When the container is run using one of the commands `train` or `predict`, this script runs the corresponding script in the `src` folder to execute the task.

## Contact Information

Hackathon created by Ready Tensor, Inc. (https://www.readytensor.ai/)
