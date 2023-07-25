# Bleached/Healthy Coral Binary Classification 
# (An End-To-End ML Project using Tensorflow)

#### Important Notes: 
If Cloning this project, go to requirements.txt and change tensorflow to tensorflow-macos and add tensorflow-metal if you intend to run on a Mac device.

If you just want to run pipeline and not the app run ```python3 main.py```

## Motivation

This project was inspired by a recent trip to Key Largo, Florida where I took a boat tour on a boat that had a clear acrylic bottom so we could see the ocean life and coral reef beneath us. And I naturally was curious if identifying bleached and healthy coral could be solved using deep learning.

<img 
    style="display: block; margin: 0 auto; width: 75%"
    src="https://imgs.mongabay.com/wp-content/uploads/sites/20/2015/10/03145905/before-after-900x600.jpg" 
    alt="Our logo">
</img>

## Simple Binary Classifaction Application

<img 
    style="display: block; margin: 0 auto; width: 75%"
    src="demo.gif" 
    alt="Our logo">
</img>

## Model Architecture: VGGNet16 + Imagenet Weights + Additional Layer for Transfer Learning

<img 
    style="display: block; margin: 0 auto; width: 75%"
    src="https://miro.medium.com/max/9999/1*_Lg1i7wv1pLpzp2F4MLrvw.png" 
    alt="Our logo">
</img>

<img 
    style="display: block; margin: 0 auto; width: 75%"
    src="https://storage.googleapis.com/lds-media/images/transfer-learning-fine-tuning-approach.original.jpg" 
    alt="Our logo">
</img>

## Project / Pipeline Structure

#### For every "stage" added to the pipeline I added to the following in this order

1. Update config.yaml
2. Update params.yaml
3. Update the entity
4. Update the configuration manager in src config
5. Update the components
6. Update the pipeline 
7. Update the main.py




# How do I run this project locally?

### Steps:

#### 1. Clone the repository

```bash
git clone https://github.com/Anish-Mitagar/End-To-End-Coral-Classification.git
```
#### 2. Create a conda environment after opening the repository

```bash
conda create -n coral python=3.9 -y
conda activate coral
```

#### 3. Install the requirements

```bash
pip3 install -r requirements.txt
```

#### 4. Run the app

```bash
python3 app.py
```



# How to do a AWS-CICD Deployment using Github Actions?

### 1. Login to AWS console.

### 2. Create IAM user for deployment

    Add the following policies:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

    Save they access key and secret (download the .csv file when shown)

	
### 3. Create ECR repo to store/save docker image
    - Save the URI for later
    - Example URI:  5283647589263.dkr.ecr.us-east-1.amazonaws.com/{$repo_name}

	
### 4. Create EC2 machine (Ubuntu) 

### 5. Connect to EC2 Machine and install Docker :
	
```bash
sudo apt-get update -y

sudo apt-get upgrade

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```

	
### 6. Configure EC2 as self-hosted runner:
    setting => actions => runner => new self hosted runner => choose os => then run command one by one

    (On the EC2 Machine name the runner "self-hosted")


### 7. Setup github secrets:

    AWS_ACCESS_KEY_ID =

    AWS_SECRET_ACCESS_KEY =

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = 

    ECR_REPOSITORY_NAME = 



