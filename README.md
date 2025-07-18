# 🦶 Diabetes Detection System

A full-stack SaaS platform that detects **early-stage diabetes** or **diabetic foot neuropathy** using plantar pressure patterns, **ESP32 sensors**, and **machine learning**.

---

## 🚀 Features

- 🔴 **Real-time Pressure Monitoring** – Plantar pressure data via ESP32 + FSR sensors  
- 🗺️ **Interactive Heatmaps** – Visualize foot pressure using D3.js / Heatmap.js  
- 🤖 **ML Prediction** – Ensemble model (CNN + MLP) for diabetes/neuropathy detection  
- 👩‍⚕️ **Patient Management** – Onboarding, session tracking, historical data  
- 📊 **Admin Dashboard** – Analytics, patient overview, model monitoring  

---

## 🛠️ Tech Stack

### 💻 Frontend
- **Framework:** Next.js  
- **Styling:** Tailwind CSS / Chakra UI  
- **Visualization:** D3.js / Heatmap.js  
- **State Management:** React Context / Redux  
- **Forms:** React Hook Form  
- **Auth:** JWT + Firebase / Auth0  

### 🔧 Backend
- **Framework:** Nest.js  
- **Database:** MongoDB / PostgreSQL  
- **WebSockets:** Socket.io  
- **Auth:** Passport.js + JWT  

### 🤖 Machine Learning
- **Frameworks:** TensorFlow/Keras, Scikit-learn  
- **Architecture:** CNN + MLP Hybrid Model  
- **API:** FastAPI  

### 🔌 Hardware
- **Microcontroller:** ESP32  
- **Sensors:** FSR (Force Sensitive Resistor) pressure sensors  
- **Communication:** WiFi + WebSocket  

---

## 📁 Project Structure
diabetes-detection/
├── client/ # Next.js frontend
│ ├── components/ # React components
│ ├── pages/ # Application routes
│ ├── lib/ # Utilities and helpers
│ └── styles/ # CSS/Tailwind config
│
├── server/ # Nest.js backend
│ ├── src/
│ │ ├── auth/ # Authentication
│ │ ├── patients/ # Patient management
│ │ ├── prediction/ # ML integration
│ │ └── gateway/ # WebSocket handling
│ └── test/ # Unit tests
│
├── model-server/ # Python ML API
│ ├── models/ # Trained models
│ ├── preprocessing/ # Data processing
│ └── app.py # FastAPI application
│
└── esp32/ # Firmware code
├── lib/ # Sensor libraries
└── main/ # Arduino sketches

yaml
Copy
Edit

---

## ⚙️ Getting Started

### 🔑 Prerequisites

- Node.js v16+  
- Python 3.8+  
- MongoDB or PostgreSQL  
- Arduino IDE (for ESP32 firmware)

---

## 🔧 Installation

### 1. Clone the repository

```bash
git clone https://github.com/Manushprajwal7/Diabetes-detection-by-CNN-MLP
cd diabetes-detection
2. Frontend Setup
bash
Copy
Edit
cd client
npm install
cp .env.example .env.local
# Update environment variables
3. Backend Setup
bash
Copy
Edit
cd ../server
npm install
cp .env.example .env
# Update environment variables
4. ML Server Setup
bash
Copy
Edit
cd ../model-server
pip install -r requirements.txt
5. ESP32 Setup
Open esp32/main/sensor_firmware.ino in Arduino IDE

Install the required libraries:

WiFi.h

ArduinoWebsockets.h

Upload the code to the ESP32 board

▶️ Running the Application
Start the backend
bash
Copy
Edit
cd server
npm run start:dev
Start the frontend
bash
Copy
Edit
cd ../client
npm run dev
Start the ML server
bash
Copy
Edit
cd ../model-server
uvicorn app:app --reload
Visit the app: http://localhost:3000

🔌 API Endpoints
🔐 Authentication
POST /auth/login – User login

POST /auth/register – User registration

👤 Patients
POST /patients/onboard – Patient onboarding

GET /patients/:id/sessions – Fetch session history

🤖 Prediction
POST /predict – Submit pressure data for prediction

📡 WebSocket
/sensor – Real-time sensor data stream

🧠 ML Model Details
🧱 Architecture
CNN Branch – Pressure matrix input

2D Convolutional layers

Max pooling

Flattening

MLP Branch – Patient metadata

Dense layers with ReLU

Fusion

Concatenation → Dense layers

🧪 Training
Dataset: Pressure matrices + patient info

Labels: Normal / Pre-Diabetic / Neuropathy

Validation: 5-fold cross-validation

Metrics: Accuracy, Precision, Recall, F1-score

🧰 Hardware Setup
🧩 Components
ESP32 DevKit V1

FSR Sensors (x3)

3.3V voltage regulator

Breadboard & jumper wires

🧷 Pin Configuration
Sensor	ESP32 GPIO
Heel	GPIO 34
Midfoot	GPIO 35
Toes	GPIO 32

🤝 Contributing
Fork the project

Create your feature branch

bash
Copy
Edit
git checkout -b feature/AmazingFeature
Commit your changes

bash
Copy
Edit
git commit -m "Add some AmazingFeature"
Push to the branch

bash
Copy
Edit
git push origin feature/AmazingFeature
Open a Pull Request 🚀

📬 Contact
Manush Prajwal
📧 Email: manushprajwal555@gmail.com
🔗 Project: GitHub Repo

vbnet
Copy
Edit


