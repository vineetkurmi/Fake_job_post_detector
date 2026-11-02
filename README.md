# Fake Job Post Detector

An AI-powered Machine Learning application that detects potentially fraudulent job postings by analyzing job descriptions, company information, employment details, and other relevant attributes.

The project uses Natural Language Processing (NLP) and Machine Learning to classify job postings and estimate the probability of fraudulent activity.

## Overview

Online job platforms sometimes contain fraudulent job advertisements designed to mislead job seekers. These postings may involve fake companies, misleading descriptions, or suspicious employment requirements.

**Fake Job Post Detector** aims to address this problem by providing an automated way to analyze job postings and identify potentially fraudulent advertisements.

Users can enter job-related information through a web interface and receive a prediction from the trained Machine Learning model.

## Features

- **Fake Job Detection:** Identifies potentially fraudulent job postings.
- **NLP-Based Analysis:** Processes textual information from job titles, company profiles, descriptions, and requirements.
- **Machine Learning Prediction:** Uses a trained classification model to predict fraudulent postings.
- **Probability Score:** Provides the estimated probability of a job posting being fraudulent.
- **Web Interface:** Simple interface for entering job information and viewing predictions.
- **FastAPI Backend:** Provides an API endpoint for model inference.
- **Docker Support:** Includes a Dockerfile for containerization.

## Tech Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Machine Learning | Scikit-learn |
| NLP | Natural Language Processing |
| Data Processing | Pandas |
| Model Serialization | Joblib |
| Backend | FastAPI |
| Frontend | HTML, CSS, JavaScript |
| Server | Uvicorn |
| Containerization | Docker |

## Project Structure

```text
Fake_job_post_detector/
│
├── Fake Job Post Detector.ipynb
│
├── app.py
│
├── index.html
│
├── fake_job_post_detector_model.pkl
│
├── requirements.txt
│
├── Dockerfile
│
├── .dockerignore
│
├── .gitignore
│
└── README.md
```

## How It Works

The application follows a simple prediction workflow:

1. **Input Collection:** Collects job title, company profile, job description, requirements, and other job-related attributes.
2. **Text Processing:** Combines the textual information into a single input for the trained model.
3. **Feature Processing:** Uses the preprocessing and feature transformation learned during model training.
4. **Model Prediction:** The trained Machine Learning model analyzes the input.
5. **Result Generation:** Returns a classification indicating whether the posting is potentially fraudulent, along with its estimated probability.

## Input Features

The application accepts the following information:

- Job Title
- Company Profile
- Job Description
- Job Requirements
- Employment Type
- Required Experience
- Required Education
- Telecommuting Availability
- Company Logo Availability
- Screening Questions Availability

## Installation and Setup

Follow these steps to run the project locally.

### 1. Clone the Repository

```bash
git clone https://github.com/vineetkurmi/Fake_job_post_detector.git
```

### 2. Navigate to the Project Directory

```bash
cd Fake_job_post_detector
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**macOS / Linux**

```bash
source venv/bin/activate
```

**Windows**

```bash
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Application

```bash
uvicorn app:app --reload
```

### 6. Open the Application

Visit the following URL in your browser:

```text
http://127.0.0.1:8000
```

FastAPI documentation is also available at:

```text
http://127.0.0.1:8000/docs
```

## API Usage

The application provides a prediction endpoint.

**Endpoint:**

```http
POST /predict
```

**Example Request:**

```json
{
  "title": "Software Developer",
  "company_profile": "Technology company",
  "description": "We are looking for a Python developer.",
  "requirements": "Knowledge of Python and SQL.",
  "employment_type": "Full-time",
  "required_experience": "Entry Level",
  "required_education": "Bachelor's Degree",
  "telecommuting": 0,
  "has_company_logo": 1,
  "has_questions": 1
}
```

**Example Response:**

```json
{
  "fraudulent": 0,
  "probability": 0.12
}
```

**Response Interpretation:**

- `fraudulent: 0` – Classified as non-fraudulent.
- `fraudulent: 1` – Classified as potentially fraudulent.
- `probability` – Estimated probability of the fraudulent class.

*Note: The example response is illustrative, not a measured model result.*

## Docker Deployment

The project includes a Dockerfile for running the application inside a container.

### Build Docker Image

```bash
docker build -t fake-job-detector .
```

### Run Docker Container

```bash
docker run -p 8000:8000 fake-job-detector
```

Open the application:

```text
http://localhost:8000
```

## Future Improvements

- Improve model performance through hyperparameter tuning.
- Experiment with advanced NLP techniques and transformer-based models.
- Add explainable AI (XAI) to understand prediction decisions.
- Improve detection of suspicious company information and job requirements.
- Evaluate model performance using precision, recall, F1-score, and confusion matrix.
- Deploy the application on a cloud platform.

## Limitations

- Predictions depend on the quality and characteristics of the training data.
- The model may produce false positives or false negatives.
- A prediction should not be treated as definitive proof of job fraud.
- Users should independently verify companies and job opportunities before sharing personal information.

## Author

**Vineet Kurmi**

- GitHub: [@vineetkurmi](https://github.com/vineetkurmi)
- LinkedIn: [Vineet Kurmi](https://www.linkedin.com/in/vineet-kurmi-916a81354/)

---

⭐ If you find this project useful, consider giving the repository a star!

**Disclaimer:** This project is intended for educational and research purposes. It is designed to assist in identifying potentially fraudulent job postings and should not replace independent verification.
