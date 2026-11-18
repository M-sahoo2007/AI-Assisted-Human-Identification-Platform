
### AI-Assisted Human Identification Platform

An AI-powered platform for identifying missing persons using facial landmark extraction and similarity matching.

[Issues](https://github.com/M-sahoo2007/Finding-missing-person-using-AI/issues?utm_source=chatgpt.com) [Stars](https://github.com/M-sahoo2007/Finding-missing-person-using-AI?utm_source=chatgpt.com) [Streamlit](https://streamlit.io/?utm_source=chatgpt.com) [MediaPipe](https://mediapipe.dev/?utm_source=chatgpt.com) [Python](https://python.org/?utm_source=chatgpt.com) [SQLite](https://sqlite.org/?utm_source=chatgpt.com)

### Disclaimer

This project is intended for educational and demonstration purposes.

Images of individuals used as sample data should be lawfully sourced and used with appropriate permission. No ownership of third-party images is claimed.

Facial landmarks and matching outputs are not proof of identity. Any potential match must be independently verified by authorized personnel before action is taken.

The system should not be used for real missing-person investigations without appropriate legal authorization, privacy safeguards, security controls, and human oversight.

### Table of Contents

* Project Overview

* The Problem

* Project Workflow

* How It Works

* Features

* System Architecture

* Getting Started

* Configuring Login Credentials

* Seeding Demo Data

* Technology Stack

* FAQ

* Developer Information

* Acknowledgements

* License

### Project Overview

The AI-Assisted Human Identification Platform is a computer vision-based application designed to assist in identifying missing persons through facial landmark extraction and similarity matching.

The platform provides an interface for registering missing-person reports, submitting potential sightings, managing case information, and comparing facial features using machine learning techniques.

It uses MediaPipe for facial landmark extraction, a K-Nearest Neighbors (KNN) algorithm for similarity comparison, and Streamlit for the application interface.

### The Problem

Missing-person cases require timely reporting, coordination, and examination of available information.

Manual photo comparison and scattered records can make it difficult to identify potential matches between missing-person reports and public sightings.

This project explores an AI-assisted approach to organizing reports and identifying visually similar faces to support the review process.

The system demonstrates how computer vision and machine learning can assist with information retrieval.

### Project Workflow

### Step 1: Register a Missing-Person Case

An authorized officer logs into the application, enters the missing person's information, and uploads a photograph.

### Step 2: Facial Landmark Extraction

MediaPipe detects facial landmarks and extracts the corresponding facial feature information.

### Step 3: Manage Cases

The dashboard displays registered cases, their current statuses, and available location-based summaries.

### Step 4: Submit Public Sightings

Members of the public can submit photographs through the separate public submission portal.

### Step 5: AI-Assisted Matching

The system uses KNN-based similarity comparison to identify potentially similar facial feature vectors.

### Step 6: Human Verification

Authorized administrators review potential matches and independently verify the available information.

A similarity result must never be treated as a confirmed identity.

### How It Works

* An officer registers a missing-person case and uploads a photograph.

* The application processes the uploaded photograph.

* MediaPipe extracts facial landmarks.

* A public user submits a potential sighting.

* The system extracts corresponding facial features from the submitted image.

* The KNN algorithm compares the available feature vectors.

* Potential matches are presented for authorized human review.

### Features

| Feature              | Description                           |
| -------------------- | ------------------------------------- |
| Face Detection       | MediaPipe Face Landmarker             |
| AI-Assisted Matching | KNN-based facial feature comparison   |
| Video Sightings      | Video frame extraction using OpenCV   |
| Dashboard            | Case statistics and status monitoring |
| Location Map         | Geographic case summaries             |
| Email Notifications  | Optional SMTP-based alerts            |
| Role-Based Access    | Admin and Officer roles               |
| Public Portal        | Separate public submission interface  |
| Database Management  | SQLite-based data storage             |

### System Architecture

The application consists of the following major components:

* Frontend: Streamlit-based user interface.

* Face Processing: MediaPipe facial landmark extraction.

* Matching Engine: KNN-based similarity comparison.

* Database: SQLite with SQLModel.

* Video Processing: OpenCV.

* Visualization: Folium interactive maps.

* Notifications: Optional SMTP integration.

### Getting Started

### Prerequisites

* Python

* pip

* Git

* Internet connection for initial model download

### 1\. Clone the Repository

```bash
git clone https://github.com/M-sahoo2007/Finding-missing-person-using-AI.git
```

### 2\. Navigate to the Project

```bash
cd Finding-missing-person-using-AI
```

### 3\. Create a Virtual Environment

```bash
python -m venv venv
```

### 4\. Activate the Virtual Environment

Windows PowerShell:

```powershell
venv\Scripts\Activate.ps1
```

Windows Command Prompt:

```cmd
venv\Scripts\activate.bat
```

macOS / Linux:

```bash
source venv/bin/activate
```

### 5\. Install Dependencies

```bash
pip install -r requirements.txt
```

### 6\. Run the Admin/Officer Portal

```bash
streamlit run Home.py
```

### 7\. Run the Public Submission Portal

```bash
streamlit run mobile_app.py
```

The SQLite database and face landmarker model are initialized according to the application configuration.

### Configuring Login Credentials

Credentials are configured through `login_config.yml`.

To generate a bcrypt password hash:

```python
import bcrypt

password = b"your_password"

hashed = bcrypt.hashpw(
    password,
    bcrypt.gensalt()
)

print(hashed.decode())
```

Edit the configuration file using the structure expected by the application.

Example:

```yaml
credentials:
  usernames:
    your_username:
      name: Your Display Name
      email: you@example.com
      city: Bhadrak
      area: Odisha
      role: Admin
      password: '$2b$12$...'
```

### Roles

| Role    | Permissions                                                 |
| ------- | ----------------------------------------------------------- |
| Admin   | Register, review, edit, and delete cases; initiate matching |
| Officer | Register cases and view authorized records                  |

Security: Never commit real credentials, password hashes, or private configuration files to GitHub. Use environment variables or a secure secrets manager for sensitive configuration where supported.

### Seeding Demo Data

The `scripts/` directory contains utilities for preparing demonstration records.

Download sample images into the reported directory:

```bash
uv run scripts/download_celebrity_images.py --dest reported
```

Or distribute images across both directories:

```bash
uv run scripts/download_celebrity_images.py --dest both
```

Run the bulk upload:

```bash
python scripts/bulk_upload.py
```

Only use sample images that you have permission to use. Avoid real sensitive personal information in demo records.

### Technology Stack

| Technology       | Purpose                    |
| ---------------- | -------------------------- |
| Python           | Main programming language  |
| Streamlit        | User interface             |
| MediaPipe Tasks  | Facial landmark extraction |
| scikit-learn KNN | Similarity matching        |
| SQLModel         | Database modelling         |
| SQLite           | Data storage               |
| Folium           | Interactive maps           |
| OpenCV           | Video processing           |

### FAQ

Q: Can I run the application offline?

The face landmarker model is downloaded during initial setup and cached locally. Offline operation depends on the application's configured features and dependencies.

Q: How accurate is facial matching?

Matching performance depends on image quality, lighting, pose, dataset composition, and model configuration. A similarity score is not a verified identity.

Q: Can I add multiple officers?

The documented configuration supports multiple user accounts and role assignments.

Q: Where is the data stored?

The documented implementation uses SQLite for database storage and local directories for images. Refer to the actual application configuration for exact locations.

Q: Can the public portal run separately?

The application provides separate Streamlit entry points for the officer/admin portal and public submission portal.

### Developer Information

Developed by: Maheswar Sahoo

* Institution: Bhadrak Institute of Engineering and Technology (BIET), Odisha

* Branch: Computer Science & Engineering (CSE)

* GitHub: [M-sahoo2007](https://github.com/M-sahoo2007?utm_source=chatgpt.com)

* Repository: [AI-Assisted Human Identification Platform](https://github.com/M-sahoo2007/Finding-missing-person-using-AI?utm_source=chatgpt.com)

### Acknowledgements

Thanks to the open-source communities and developers behind Python, Streamlit, MediaPipe, OpenCV, scikit-learn, SQLModel, and SQLite.

### License

Add the appropriate `LICENSE` file to this repository before specifying a license.

Project Title: AI-Assisted Human Identification Platform

Developed by: Maheswar Sahoo

Institution: Bhadrak Institute of Engineering and Technology (BIET), Odisha

