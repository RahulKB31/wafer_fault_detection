# Wafer Fault Detection ML Project

This repository contains the code and resources for a machine learning project focused on wafer fault detection. The goal of the project is to build a predictive model that can classify wafers as either working (+1) or faulty (-1) based on sensor data. The project involves data validation, database operations, model training, and deployment on AWS Elastic Beanstalk.

## Table of Contents

- [Project Overview](#wafer-fault-detection-ml-project)
- [Table of Contents](#table-of-contents)
- [Problem Statement](#problem-statement)
- [Data Description](#data-description)
- [Data Validation](#data-validation)
- [Data Insertion in Database](#data-insertion-in-database)
- [Model Training](#model-training)
- [Prediction](#prediction)
- [Deployment](#deployment)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Problem Statement

The aim of this project is to develop a machine learning model capable of predicting whether a wafer is working (+1) or faulty (-1) based on sensor data. The project involves data preprocessing, model training, and deployment of the predictive model on AWS Elastic Beanstalk.

## Data Description

The dataset contains wafer sensor data in CSV format. Each file represents a batch of wafers, with each row representing a wafer and its corresponding sensor values. The last column of the data indicates whether the wafer is good (+1) or bad (-1).

## Data Validation

The data goes through rigorous validation steps, including checks for file name patterns, number of columns, column names, data types, and null values. Invalid files are moved to the "Bad_Data_Folder".

## Data Insertion in Database

Validated data is inserted into a database table named "Good_Data" for further processing and model training.

## Model Training

The preprocessed data is used to train KMeans clustering models. For each cluster, the best model (Random Forest or XGBoost) is selected based on AUC scores.

## Prediction

Incoming data goes through validation similar to the training data. Validated data is then preprocessed, clustered using the pre-trained KMeans model, and predictions are made using the appropriate model for each cluster.

## Deployment

The project is deployed on AWS Elastic Beanstalk for easy scalability and management. The Flask framework is used to create a web application for the project's front end.

## Project Structure

The project is structured as follows:

- `data_validation.py`: Contains data validation functions.
- `database_operations.py`: Handles database operations.
- `model_training.py`: Implements model training and selection.
- `prediction.py`: Handles prediction using the trained models.
- `app.py`: Implements the Flask web application for the project's front end.
- `requirements.txt`: Lists project dependencies.
- `config.json`: Contains configuration settings.
- `schema.json`: Defines schema for data validation.
- `logo.png`: Project logo.

## Getting Started

1. Clone this repository.
2. Install the required dependencies using `pip install -r requirements.txt`.
3. Configure the `config.json` and `schema.json` files according to your data and requirements.
4. Run the Flask application using `python app.py`.

## Dependencies

The project uses the following main dependencies:

- Flask
- Pandas
- Scikit-learn
- XGBoost

Refer to `requirements.txt` for a complete list of dependencies.

## Usage

1. Upload your training data files to the designated folder.
2. Configure the `config.json` and `schema.json` files.
3. Run the data validation, insertion, and model training scripts.
4. Deploy the project on AWS Elastic Beanstalk.
5. Use the provided web interface to interact with the deployed project.

## Contributing

Contributions are welcome! If you find any issues or want to enhance the project, feel free to open a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
