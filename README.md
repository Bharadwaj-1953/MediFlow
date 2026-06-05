<h1 align="center">
Cloud-Native Medical Data Integration and <br> Mining System
</h1>

---

## 📝 Abstract

<div align="justify">

MediFlow is a cloud-native application built on AWS for integrating and analyzing distributed medical data across healthcare systems. MediFlow aims to support healthcare professionals by providing real-time access to multi-source medical information while preserving user privacy. The system uses four modules (Admin, Doctor, Patient, IOH) and securely stores medical data in AWS S3 buckets.

MediFlow leverages the **Internet of Health (IoH)** paradigm and implements privacy-aware techniques like **Locality Sensitive Hashing (LSH)** to handle multi-source data mining and retrieval efficiently. The project is deployed on **AWS EC2**, ensuring scalable computation and secure data storage.

</div>

---

## 🎯 Objectives

- Enable secure, privacy-respecting integration of medical data across healthcare sources.
- Design and implement a scalable 4-module architecture (Admin, Doctor, Patient, IOH).
- Use **Locality Sensitive Hashing (LSH)** for multi-source data integration and privacy-preserving record search.
- Leverage **AWS S3** for secure, cost-effective storage.
- Enhance diagnostic accuracy and clinical decision-making using real-time data.

---

## 📦 Technologies Used

- **Backend**: Python 3.6+, Flask
- **Frontend**: HTML5, CSS, Bootstrap, JavaScript
- **Database**: MySQL (XAMPP / SQLyog)
- **Cloud Services**: AWS EC2 (deployment), AWS S3 (storage)
- **Libraries**: Flask, Pandas, NumPy, MySQL Connector, smtplib
- **IDE**: PyCharm / VS Code

---

## ⚙️ System Modules

### 🧑‍💼 Admin Module
- Login, manage doctors and patients
- Request/view medicine approvals from IOH
- Track appointment status and notify patients

### 🩺 Doctor Module
- Register/Login
- View and accept/reject appointment requests
- Upload patient reports and prescribe medication

### 🧑‍⚕️ Patient Module
- Register/Login
- View doctors and request appointments
- Track appointment status and view prescriptions

### 🌐 IOH Module
- Login securely
- View patient disease data
- Upload medicine recommendations
- Approve or reject medicine requests from Admin

---

## 🧪 Working Methodology

1. Clone the project
2. Run the full setup script (below)
3. Launch the Flask server
4. Connect to MySQL and AWS S3
5. Use browser to interact with all modules

---

## 🚀 Bash Setup Script

Save the below script as `setup.sh` and run it on Ubuntu:

```bash
#!/bin/bash

# Update and install dependencies
sudo apt update && sudo apt install -y python3 python3-pip mysql-server

# Install pip packages
pip3 install flask pandas numpy mysql-connector-python boto3

# Clone the repository (skip if already cloned)
# git clone https://github.com/Bharadwaj-1953/AWS-MedData.git
# cd AWS-MedData

# Set up MySQL service
sudo service mysql start

# Create database and user
echo "Creating MySQL database..."
mysql -u root -e "CREATE DATABASE mediflow_db;
  CREATE USER 'mediuser'@'localhost' IDENTIFIED BY 'medipass';
  GRANT ALL PRIVILEGES ON mediflow_db.* TO 'mediuser'@'localhost';
  FLUSH PRIVILEGES;"

# Show confirmation
echo "MySQL setup complete. Now configure DB connection in your Flask app."

# Export Flask environment variables
export FLASK_APP=app.py
export FLASK_ENV=development

# (Optional) Run Flask server
# flask run --host=0.0.0.0 --port=5000

echo "✅ Environment ready. Use 'flask run' to start the server."
```

To run it:

```bash
chmod +x setup.sh
./setup.sh
```

---

## 📂 Project Structure

```
MediFlow/
├── app.py                # Main Flask application
├── templates/            # HTML pages
│   ├── login.html
│   ├── dashboard.html
│   └── ...
├── static/               # CSS, JS
├── config.py             # DB/S3 credentials
├── modules/
│   ├── admin.py
│   ├── doctor.py
│   ├── patient.py
│   └── ioh.py
└── requirements.txt
```

---

## 📈 Future Enhancements

- Integrate AI-based disease prediction from uploaded symptoms
- Implement MFA (e.g., OTP verification)
- Add audit logging and analytics dashboard
- Extend support for real-time IoT health devices

---

## 🛡️ Security Considerations

- Passwords hashed, sessions isolated per user type
- AWS S3 access via IAM roles and environment variables
- Database interactions sanitized to prevent SQL injection

---

## 📊 Results, Analysis, and Complexity

<div align="justify">

For detailed performance results, complexity analysis, scalability observations, and additional experimental outputs, please feel free to contact me.

</div>

---

## 📬 Contact Information

- **Email**: manne.bharadwaj.1953@gmail.com
- **LinkedIn**: [Bharadwaj Manne](https://www.linkedin.com/in/bharadwaj-manne-711476249/)
