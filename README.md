AI-Assisted Human Identification Platform

An AI-powered platform for identifying missing persons using facial landmark extraction and similarity matching.

""Issues" (https://img.shields.io/github/issues/M-sahoo2007/Finding-missing-person-using-AI)" (https://github.com/M-sahoo2007/Finding-missing-person-using-AI/issues)
""Stars" (https://img.shields.io/github/stars/M-sahoo2007/Finding-missing-person-using-AI?style=social)" (https://github.com/M-sahoo2007/Finding-missing-person-using-AI)
""Streamlit" (https://img.shields.io/badge/Streamlit-000000?style=for-the-badge&logo=streamlit&logoColor=white)" (https://streamlit.io/)
""MediaPipe" (https://img.shields.io/badge/MediaPipe-000000?style=for-the-badge&logo=mediapipe&logoColor=white)" (https://mediapipe.dev/)
""Python" (https://img.shields.io/badge/Python-000000?style=for-the-badge&logo=python&logoColor=white)" (https://python.org/)
""SQLite" (https://img.shields.io/badge/SQLite-000000?style=for-the-badge&logo=sqlite&logoColor=white)" (https://sqlite.org/)

---

Project Overview

The AI-Assisted Human Identification Platform is a computer vision-based application designed to assist in identifying missing persons through facial landmark extraction and similarity matching.

The platform provides an interface for registering missing-person reports, submitting potential sightings, managing case information, and comparing facial features using machine learning techniques.

It uses MediaPipe for facial landmark extraction, a K-Nearest Neighbors (KNN) algorithm for similarity comparison, and Streamlit for the application interface.

Disclaimer

This project is developed for educational and demonstration purposes.

Facial matching results are not proof of identity. Every potential match requires independent verification by authorized personnel.

The system must not be used for actual missing-person investigations without appropriate legal authorization, privacy safeguards, security controls, and human oversight.

Table of Contents

- Project Overview
- Problem Statement
- Project Workflow
- How the System Works
- Features
- System Architecture
- Installation and Setup
- Login Configuration
- Demo Data
- Technology Stack
- FAQ
- Developer Information
- Acknowledgements

Problem Statement

Missing-person cases require timely reporting, coordination, and examination of available information.

Manual photograph comparison and scattered records can make it difficult to identify potential matches between missing-person reports and public sightings.

This project proposes an AI-assisted approach to organizing reports and identifying visually similar faces using computer vision and machine learning.

Project Workflow

Step 1: Register a Missing-Person Case

An authorized officer logs into the application, enters the missing person's information, and uploads a photograph.

Step 2: Facial Landmark Extraction

MediaPipe detects facial landmarks and extracts the corresponding facial feature information.

Step 3: Manage Cases

The dashboard displays registered cases, their statuses, and available location-based summaries.

Step 4: Submit Public Sightings

Members of the public can submit photographs through the separate public submission portal.

Step 5: AI-Assisted Matching

The system uses KNN-based similarity comparison to identify potentially similar facial feature vectors.

Step 6: Human Verification

Authorized administrators review potential matches and independently verify the available information.

How the System Works

1. An officer registers a missing-person case.
2. The application processes the uploaded photograph.
3. MediaPipe extracts facial landmarks.
4. A public user submits a potential sighting.
5. The system extracts facial features from the submitted image.
6. The KNN algorithm compares available feature vectors.
7. Potential matches are displayed for authorized human review.

Key Features

Feature| Description
Face Detection| MediaPipe Face Landmarker
AI-Assisted Matching| KNN-based facial feature comparison
Video Sightings| Video frame extraction using OpenCV
Admin Dashboard| Case statistics and monitoring
Location Map| Geographic case summaries
Email Notifications| Optional SMTP-based alerts
Role-Based Access| Admin and Officer roles
Public Portal| Separate public submission interface
Database Management| SQLite-based data storage

System Architecture

The application consists of the following major components:

1. Frontend: Streamlit-based user interface.
2. Face Processing: MediaPipe facial landmark extraction.
3. Matching Engine: KNN-based similarity comparison.
4. Database: SQLite with SQLModel.
5. Video Processing: OpenCV.
6. Visualization: Folium interactive maps.
7. Notifications: Optional SMTP integration.

Installation and Setup

Prerequisites

- Python
- pip
- Git
- Internet connection for initial model download

1. Clone the Repository

git clone https://github.com/M-sahoo2007/Finding-missing-person-using-AI.git

2. Navigate to the Project

cd Finding-missing-person-using-AI

3. Create a Virtual Environment

python -m venv venv

Activate it on Windows:

venv\Scripts\activate

Activate it on macOS/Linux:

source venv/bin/activate

4. Install Dependencies

pip install -r requirements.txt

5. Run the Admin/Officer Portal

streamlit run Home.py

6. Run the Public Submission Portal

streamlit run mobile_app.py

Login Configuration

User credentials are configured through "login_config.yml".

Generate a bcrypt password hash:

import bcrypt

password = b"your_password"

hashed = bcrypt.hashpw(
    password,
    bcrypt.gensalt()
)

print(hashed.decode())

Configure the login credentials using the structure expected by the application.

Never commit real credentials, password hashes, or private configuration files to GitHub.

Demo Data

The "scripts/" directory contains utilities for preparing demonstration records.

Download sample images:

uv run scripts/download_celebrity_images.py --dest reported

Or distribute images across both directories:

uv run scripts/download_celebrity_images.py --dest both

Run bulk upload:

python scripts/bulk_upload.py

Only use images that you have permission to use.

Technology Stack

Technology| Purpose
Python| Main programming language
Streamlit| User interface
MediaPipe Tasks| Facial landmark extraction
scikit-learn| KNN similarity matching
SQLModel| Database modelling
SQLite| Data storage
Folium| Interactive maps
OpenCV| Video processing

FAQ

Q: What is the purpose of this project?

To demonstrate how artificial intelligence and computer vision can assist in organizing missing-person reports and identifying potentially similar faces.

Q: Can the application work offline?

The face landmarker model is downloaded during initial setup and cached locally. Offline operation depends on the configured features and dependencies.

Q: How accurate is facial matching?

Performance depends on image quality, lighting, pose, dataset composition, and model configuration. A similarity score is not a verified identity.

Q: Can multiple officers use the platform?

The documented configuration supports multiple user accounts and role assignments.

Q: Where is the data stored?

The documented implementation uses SQLite for database storage and local directories for images.

Developer Information

Developed by: Maheswar Sahoo

- Institution: Bhadrak Institute of Engineering and Technology (BIET), Odisha
- Department: Computer Science & Engineering
- GitHub: "M-sahoo2007" (https://github.com/M-sahoo2007)

Acknowledgements

Special thanks to the open-source communities and developers behind Python, Streamlit, MediaPipe, OpenCV, scikit-learn, SQLModel, and SQLite.

License

Add an appropriate LICENSE file to this repository before specifying a license.

---

Project Title: AI-Assisted Human Identification Platform

Developed by Maheswar Sahoo
Bhadrak Institute of Engineering and Technology (BIET), Odisha
