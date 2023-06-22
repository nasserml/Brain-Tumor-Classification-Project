# Brain-Tumor-Classification--Project


## Workflows

1. Update config.yaml
2. Update secrets.yaml [Optional]
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py
9. Update the dvc.yaml


# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/nasserml/Brain-Tumor-Classification-Project
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n cnncls python=3.8 -y
```

```bash
conda activate cnncls
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```


### DVC cmd

1. dvc init
2. dvc repro
3. dvc dag



# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/brain

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app




# AZURE-CICD-Deployment-with-Github-Actions

## Save pass:

s3cEZKH5yytiVnJ3h+eI3qhhzf9q1vNwEi6+q+WGdd+ACRCZ7JD6


## Run from terminal:

docker build -t brainapp.azurecr.io/brain:latest .

docker login brainapp.azurecr.io

docker push brainenapp.azurecr.io/brain:latest


## Deployment Steps:

1. Build the Docker image of the Source Code
2. Push the Docker image to Container Registry
3. Launch the Web App Server in Azure 
4. Pull the Docker image from the container registry to Web App server and run




# Brain Tumor Classification Project

This repository contains an end-to-end machine learning project for brain tumor classification.

## Project Structure

- [`.dvc`](.dvc): Contains DVC (Data Version Control) files for tracking data and models.
- [`.gitignore`](.gitignore): Specifies the files and directories to be ignored by Git.
- `config`: Directory containing configuration files.
    - [`config.yaml`](config/config.yaml): Configuration file for the project.
- [`.github/workflows`](.github/workflows): GitHub Actions workflow configuration files.
    - [`.gitkeep`](.github/workflows/.gitkeep): Placeholder file to keep the directory structure in version control.
- `research`: Directory containing Jupyter notebooks related to data analysis and experimentation.
    - [`01_data_ingestion.ipynb`](research/01_data_ingestion.ipynb): Notebook for data ingestion.
    - [`02_prepare_base_model.ipynb`](research/02_prepare_base_model.ipynb): Notebook for preparing the base model.
    - [`03_prepare_callbacks.ipynb`](research/03_prepare_callbacks.ipynb): Notebook for preparing the callbacks.
    - [`04_training.ipynb`](research/04_training.ipynb): Notebook for model training.
    - [`05_model_evaluation.ipynb`](research/05_model_evaluation.ipynb): Notebook for model evaluation.
    - [`trials.ipynb`](research/trials.ipynb): Notebook for experimental trials.
- `src/cnnClassifier`: Source code directory for the CNN Classifier.
    - `components`: Directory containing the components of the CNN Classifier.
        - [`__init__.py`](src/cnnClassifier/components/__init__.py): Initialization file for the components module.
        - [`data_ingestion.py`](src/cnnClassifier/components/data_ingestion.py): Module for data ingestion.
        - [`evaluation.py`](src/cnnClassifier/components/evaluation.py): Module for evaluation.
        - [`prepare_base_model.py`](src/cnnClassifier/components/prepare_base_model.py): Module for preparing the base model.
        - [`prepare_callbacks.py`](src/cnnClassifier/components/prepare_callbacks.py): Module for preparing the callbacks.
        - [`training.py`](src/cnnClassifier/components/training.py): Module for model training.
    - `config`: Directory containing the configuration files for the CNN Classifier.
        - [`__init__.py`](src/cnnClassifier/config/__init__.py): Initialization file for the config module.
        - [`configuration.py`](src/cnnClassifier/config/configuration.py): Module for configuration settings.
    - `constants`: Directory containing constant values used in the CNN Classifier.
        - [`__init__.py`](src/cnnClassifier/constants/__init__.py): Initialization file for the constants module.
    - `entity`: Directory containing entity classes used in the CNN Classifier.
        - [`__init__.py`](src/cnnClassifier/entity/__init__.py): Initialization file for the entity module.
        - [`config_entity.py`](src/cnnClassifier/entity/config_entity.py): Entity class for configuration.
    - `pipeline`: Directory containing the pipeline modules for the CNN Classifier.
        - [`__init__.py`](src/cnnClassifier/pipeline/__init__.py): Initialization file for the pipeline module.
        - [`predict.py`](src/cnnClassifier/pipeline/predict.py): Module for prediction.
        - [`stage_01_data_ingestion.py`](src/cnnClassifier/pipeline/stage_01_data_ingestion.py): Script for stage 1 - data ingestion.
        - [`stage_02_prepare_base_model.py`](src/cnnClassifier/pipeline/stage_02_prepare_base_model.py): Script for stage 2 - preparing the base model.
        - [`stage_03_training.py`](src/cnnClassifier/pipeline/stage_03_training.py): Script for stage 3 - model training.
        - [`stage_04_evaluation.py`](src/cnnClassifier/pipeline/stage_04_evaluation.py): Script for stage 4 - model evaluation.
    - `utils`: Directory containing utility modules for the CNN Classifier.
        - [`__init__.py`](src/cnnClassifier/utils/__init__.py): Initialization file for the utils module.
        - [`common.py`](src/cnnClassifier/utils/common.py): Common utility functions.
- `templates`: Directory containing templates.
    - [`index.html`](templates/index.html): HTML template file.
- [`.dvcignore`](.dvcignore): Specifies the files and directories to be ignored by DVC.
- [`.gitignore`](.gitignore): Specifies the files and directories to be ignored by Git.
- [`LICENSE`](LICENSE): License file for the project.
- [`README.md`](README.md): Project README file.
- [`app.py`](app.py): Flask application file.
- [`dvc.lock`](dvc.lock): DVC lock file.
- [`dvc.yaml`](dvc.yaml): DVC YAML configuration file.
- [`inputImage.jpg`](inputImage.jpg): Sample input image file.
- [`main.py`](main.py): Main Python script for the project.
- [`params.yaml`](params.yaml): YAML file for model parameters.
- [`requirements.txt`](requirements.txt): Required Python packages for the project.
- [`scores.json`](scores.json): JSON file containing model scores.
- [`setup.py`](setup.py): Setup script for packaging the project.
- [`template.py`](template.py): Template Python script.


## Getting Started

To get started with the project, follow the instructions below:

1. Clone the repository: `git clone https://github.com/nasserml/Brain-Tumor-Classification-Project.git`
2. Install the dependencies: `pip install -r requirements.txt`
3. Configure the project parameters in `params.yaml`.
4. Run the application: `python app.py`
5. Access the text summarization API at `http://localhost:8080`.

## License

This project is licensed under the [MIT License](LICENSE).


