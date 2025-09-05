Forest Fire Prediction Web App
This project is an end-to-end machine learning application that predicts the area affected by forest fires using a ridge regression model. Built with Flask, it provides a web interface for users to input environmental features (e.g., Temperature, Relative Humidity, Wind Speed) and receive predictions. The project demonstrates skills in data preprocessing, model training, and deployment, making it a strong addition to a beginner's portfolio.
Table of Contents

Project Overview
Features
Installation
Usage
File Structure
Design for Manufacturability (DFM) Considerations
Future Improvements
License

Project Overview
This web application uses a trained ridge regression model to predict forest fire area based on inputs like Temperature, Relative Humidity (RH), Wind Speed (Ws), Rainfall, Fire Weather Index components (FFMC, DMC, ISI), fire class, and region. The model is pre-trained, serialized using pickle, and deployed via a Flask web server. Data preprocessing is handled with StandardScaler for feature scaling.
The app features:

A user-friendly interface (index.html, home.html) for inputting features and viewing predictions.
Backend processing with Flask and scikit-learn.
Modular code structure for scalability and maintenance.

Features

Input Features: Accepts 9 environmental variables (Temperature, RH, Ws, Rain, FFMC, DMC, ISI, Classes, Region).
Prediction: Outputs the predicted fire area using a ridge regression model.
Web Interface: Simple HTML forms for user interaction, served via Flask.
Preprocessing: Scales input data using a pre-trained StandardScaler.
Deployment: Runs locally or can be hosted on platforms like Heroku.

Installation

Clone the Repository:
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name


Set Up a Virtual Environment (recommended):
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


Install Dependencies:Ensure you have Python 3.8+ installed. Then, install required packages:
pip install flask numpy pandas scikit-learn


Verify Model Files:Ensure the models/ directory contains:

ridge.pkl: Pre-trained ridge regression model.
scaler.pkl: Pre-trained StandardScaler.

If these are missing, train the model using your dataset (see Future Improvements).


Usage

Run the Application:
python app.py

The app will start a local server at http://0.0.0.0:5000.

Access the Web Interface:

Open a browser and navigate to http://localhost:5000.
Enter values for the 9 input features (e.g., Temperature, RH) in the form.
Submit to view the predicted fire area on the results page.


Example Input:

Temperature: 30.0 (°C)
RH: 65 (%)
Ws: 15 (km/h)
Rain: 0.0 (mm)
FFMC: 85.0
DMC: 20.0
ISI: 5.0
Classes: 1 (fire/not fire)
Region: 0 (e.g., Bejaia region)



File Structure
ML-END-TO-END-PROJECT/
├── models/
│   ├── ridge.pkl        # Trained ridge regression model
│   ├── scaler.pkl       # Trained StandardScaler
├── templates/
│   ├── index.html       # Landing page with input form
│   ├── home.html        # Results page
├── app.py               # Main Flask application
├── README.md            # Project documentation

Design for Manufacturability (DFM) Considerations
In software terms, DFM translates to designing for scalability, maintainability, and deployment ease:

Simplicity: Uses minimal dependencies (Flask, scikit-learn, etc.) to reduce setup complexity.
Modularity: Separates model logic (ridge.pkl, scaler.pkl) from app logic (app.py) for easy updates.
Standardization: Leverages standard Python libraries and Flask for compatibility across platforms.
Scalability: Flask app can be deployed to cloud platforms (e.g., Heroku) with minimal changes.
Error Handling: Basic POST/GET routing; future versions can add input validation for robustness.

Future Improvements

Add input validation to handle invalid user inputs (e.g., non-numeric values).
Include model training script to regenerate ridge.pkl and scaler.pkl.
Enhance UI with CSS/JavaScript for better user experience.
Deploy to a cloud platform like Heroku or AWS for public access.
Add API endpoints for programmatic access to predictions.

License
This project is licensed under the MIT License. See the LICENSE file for details.
