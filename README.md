# Dockerized ML Application for Iris Prediction

This project is a simple machine learning web application that predicts the species of an Iris flower based on four input features. The application uses a decision tree classifier and is built with Python, Flask, and Scikit-Learn, containerized using Docker for easy deployment.

## Overview of the Project
The goal of this project is to create a Dockerized machine learning application for predicting Iris flower species. The application takes four input features—sepal length, sepal width, petal length, and petal width—and uses a decision tree model to predict whether the Iris flower is of species Setosa, Versicolor, or Virginica.

The entire application has been containerized using Docker, allowing easy deployment and scaling. This project serves as a demonstration of Docker usage for ML applications, GCP deployment, and creating a REST API using Flask.

## Technologies Used
- **Python 3.9**
- **Flask** - for building the web server
- **Scikit-Learn** - for the machine learning model
- **Docker** - for containerization
- **Google Cloud Platform (GCP)** - for cloud deployment

## Instructions to Build and Run the Docker Container

### Prerequisites
- **Docker** should be installed on your local machine.
- **Git** should be installed.

### Steps to Set Up the Project Locally
1. **Clone the repository**:
    ```sh
    git clone https://github.com/arshia-pelathur/dockerized-ML-app-iris-prediction.git
    cd dockerized-ML-app-iris-prediction
    ```

2. **Build the Docker Image**:
    - Run the following command to build the Docker image from the Dockerfile in the project directory:
    ```sh
    sudo docker build -t ml-app .
    ```

3. **Run the Docker Container**:
    - Use the following command to run the container, exposing port `4000`:
    ```sh
    sudo docker run -p 4000:80 ml-app
    ```
    - After running the container, the application will be accessible on `http://localhost:4000`.

## Instructions to Test the ML Endpoint

### Web Interface
After running the Docker container, access the landing page of the application by visiting `http://localhost:4000` in your browser. You should see a simple greeting message confirming the application is running.

### API Endpoint
The application provides a `/predict` endpoint for making predictions. You can use `curl` or a tool like Postman to send a POST request with the required JSON data.

**Example Request Using `curl`**:
```sh
curl -X POST http://localhost:4000/predict -H "Content-Type: application/json" -d '{"input": [5.1, 3.5, 1.4, 0.2]}'

**Example Response**:
```json
{
  "prediction": 0
}

## Any Other Relevant Information About the Project

### Project Structure
- **`Dockerfile`**: Contains the instructions to create a Docker image of the application.
- **`requirements.txt`**: Lists the Python dependencies required for the project.
- **`train_model.py`**: Script to train the decision tree classifier and save the model as `model.pkl`.
- **`app.py`**: Flask application code to serve predictions using the trained model.
- **`model.pkl`**: Serialized machine learning model for Iris species classification.
