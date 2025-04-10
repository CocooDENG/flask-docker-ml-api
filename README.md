This project provides a lightweight Flask-based API designed to estimate stakeholder engagement scores using a linear regression model grounded in the Rubin Causal Model framework. The model predicts outcomes based on treatment status (w) and sustainability spending (x).
## Project Structure
app.py: Contains the Flask server and a /predict endpoint. It trains a linear regression model and returns predicted engagement scores based on input parameters (w, x).

Dockerfile: Defines the Docker container with Python 3.10 and necessary dependencies, ensuring a consistent and isolated runtime environment.

requirements.txt: Lists the required Python packages (flask, scikit-learn, numpy) to run the API inside Docker.

## How to Run the Project

### Step 1: Build the Docker image
```bash
docker build -t causal-api .

### Step 2: Run the Docker container
```bash
docker run -p 5000:5000 causal-api

The API will be accessible at http://localhost:5000/predict.

