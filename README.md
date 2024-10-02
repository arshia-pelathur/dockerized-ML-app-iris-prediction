# Dockerized ML App for Iris Prediction

This project is a simple machine learning web application for predicting Iris flower species using a decision tree classifier. The application is built with Python, Flask, and Scikit-Learn, and is containerized using Docker for easy deployment. The project also demonstrates deployment on Google Cloud Platform (GCP) for cloud-based accessibility.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Technologies Used](#technologies-used)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Project Structure](#project-structure)
6. [Contributing](#contributing)
7. [License](#license)

## Project Overview
The goal of this project is to create a machine learning application, containerize it using Docker, and make it accessible through an HTTP API. The application takes input features for Iris flowers and predicts the species using a pre-trained model. Additionally, the app is deployed on Google Cloud Platform for remote usage.

## Technologies Used
- Python 3.9
- Flask
- Scikit-Learn
- Docker
- Google Cloud Platform (GCP)

## Installation

### Prerequisites
- Docker installed on your system
- Git installed

### Steps
1. **Clone the repository:**
    ```sh
    git clone https://github.com/arshia-pelathur/dockerized-ML-app-iris-prediction.git
    cd dockerized-ML-app-iris-prediction
    ```

2. **Build the Docker image:**
    ```sh
    sudo docker build -t ml-app .
    ```

3. **Run the Docker container:**
    ```sh
    sudo docker run -p 4000:80 ml-app
    ```

    This command will make the application accessible on `http://localhost:4000`.

## Usage
### Web Interface
After running the Docker container, you can access the default landing page by visiting `http://localhost:4000` in your browser.

### API Endpoint
The application exposes a `/predict` endpoint for making predictions. You can use tools like `curl` or Postman to send a POST request with JSON data.

**Example Request:**
```sh
curl -X POST http://localhost:4000/predict -H "Content-Type: application/json" -d '{"input": [5.1, 3.5, 1.4, 0.2]}'
```sh

## Project Structure

- Dockerfile: Instructions to create a Docker image of the application.
- requirements.txt: Python dependencies for the project.
- train_model.py: Script to train the decision tree model and save it.
- app.py: Flask application code for serving predictions.
- model.pkl: Pre-trained machine learning model.
