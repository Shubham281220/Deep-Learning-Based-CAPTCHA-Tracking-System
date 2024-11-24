markdown
# Deep Learning-Based CAPTCHA Tracking System

**Captcha-Tracking-System** is a Flask-based web application designed for CAPTCHA recognition and user authentication. The project supports multiple CAPTCHA types, enabling automation of tasks that require CAPTCHA processing and user authentication through a secure interface.

---

## Features

### CAPTCHA Recognition:
- Processes CAPTCHAs using deep learning models built with TensorFlow and Keras.
- Custom preprocessing pipelines for different CAPTCHA types (GST, SBI, and TDS).

### User Authentication:
- Secure user login and registration with session management.
- MySQL database integration for storing user credentials.

### Web Application:
- Responsive interface powered by Flask and HTML templates.

### Scalable Design:
- Modular code structure for easy addition of new CAPTCHA types and features.

---

## Supported CAPTCHA Types
- **GST:**
  - Numeric-only CAPTCHAs.
  - Example characters: `0, 1, 2, ... 9`.

- **SBI:**
  - Alphanumeric CAPTCHAs.
  - Example characters: `2, 3, 4, b, c, d, e`.

- **TDS:**
  - Advanced alphanumeric CAPTCHAs.
  - Example characters: `0, 2, 3, A, B, C, ... Z`.

Each type uses a dedicated pre-trained model configured in `captcha_parameters.json`.

---

## Use Case
On a smaller scale, this project could automate routine tasks that require bypassing CAPTCHA without human intervention. At an industry level, this system could significantly enhance automation in web scraping, enabling faster data collection for analytics, research, or business intelligence. It could be scaled in e-commerce, finance, or market research, automating large-scale data extraction from websites requiring CAPTCHA verification.

---

## Installation and Environment Setup

### Step 1: Clone the Repository
bash
git clone https://github.com/yourusername/Deep-Learning-Based-CAPTCHA-Tracking-System.git
cd Deep-Learning-Based-CAPTCHA-Tracking-System


### Step 2: Set Up Python Environment
1. Install Python (3.7 or higher).
2. Create and activate a virtual environment:
   bash
   python -m venv env
   source env/bin/activate  # On Windows: .\env\Scripts\activate
   
3. Install required Python libraries:
   bash
   pip install flask flask-mysqldb Pillow tensorflow keras opencv-python
   

### Step 3: Database Setup
1. Install MySQL and create a database named `captchalogin`.
2. Create a table named `accounts`:
   sql
   CREATE TABLE accounts (
       id INT AUTO_INCREMENT PRIMARY KEY,
       username VARCHAR(50) NOT NULL,
       password VARCHAR(255) NOT NULL,
       email VARCHAR(100) NOT NULL
   );
   

### Step 4: Prepare CAPTCHA Models
- Place the pre-trained model files (`gst_ctc_v2.h5`, `sbi_ctc_v1.h5`, `tds_ctc_v1.h5`) in the project directory.

### Step 5: Run the Application
- Start the Flask application:
  bash
  python app.py
  
- Access the application in your browser at `http://127.0.0.1:5000/`.

---

## Project Structure
plaintext
Captcha-Tracking-Bot/
├── app.py                # Main Flask application
├── captcha.py            # CAPTCHA processing logic
├── captcha_parameters.json  # Parameters for CAPTCHA processing
├── gst_ctc_v2.h5         # GST CAPTCHA model
├── sbi_ctc_v1.h5         # SBI CAPTCHA model
├── tds_ctc_v1.h5         # TDS CAPTCHA model
├── settings.py           # CAPTCHA model configuration
├── templates/            # HTML templates for the web interface
├── static/               # Static assets (e.g., CSS, images)
├── README.md             # Project documentation


---

## Technologies Used
- **Backend:** Flask
- **Frontend:** HTML, CSS (via Flask templates)
- **Database:** MySQL
- **Machine Learning:** TensorFlow, Keras
- **Image Processing:** OpenCV, PIL
