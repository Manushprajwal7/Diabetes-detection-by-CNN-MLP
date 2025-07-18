
Diabetes Detection System

A full-stack SaaS platform that detects early-stage diabetes or diabetic foot neuropathy using plantar pressure patterns, ESP32 sensors, and machine learning.



 Features

- Real-time Pressure Monitoring: Plantar pressure data collection via ESP32 and FSR sensors
- Interactive Heatmaps: Visualize foot pressure distribution using D3.js/Heatmap.js
- ML Prediction: Ensemble model (CNN + MLP) for diabetes/neuropathy detection
- Patient Management: Comprehensive onboarding and session tracking
- Admin Dashboard: Analytics, patient management, and model monitoring

 Tech Stack

 Frontend
- Framework: Next.js
- Styling: Tailwind CSS / Chakra UI
- Visualization: D3.js/Heatmap.js
- State Management: React Context/Redux
- Forms: React Hook Form
- Auth: JWT + Firebase/Auth0

 Backend
- Framewor: Nest.js
- Database: MongoDB/PostgreSQL
- WebSockets: Socket.io
- Auth: Passport.js JWT

 Machine Learning
- Frameworks: TensorFlow/Keras, Scikit-learn
- Model Architecture: CNN + MLP hybrid
- API: FastAPI

Hardware
- Microcontroller: ESP32
- Sensors: FSR pressure sensors
- Protocol: WiFi + WebSocket

 Project Structure
diabetes-detection/
├── client/  Next.js frontend
│ ├── components/  React components
│ ├── pages/  Application routes
│ ├── lib/  Utilities and helpers
│ └── styles/  CSS/Tailwind config
│
├── server/  Nest.js backend
│ ├── src/
│ │ ├── auth/  Authentication
│ │ ├── patients/  Patient management
│ │ ├── prediction/  ML integration
│ │ └── gateway/# WebSocket handling
│ └── test/  Unit tests
│
├── model-server/  Python ML API
│ ├── models/  Trained models
│ ├── preprocessing/  Data processing
│ └── app.py  FastAPI application
│
└── esp32/ Firmware code
├── lib/  Sensor libraries
└── main/  Arduino sketches

Getting Started

 Prerequisites

- Node.js v16+
- Python 3.8+
- MongoDB/PostgreSQL
- Arduino IDE (for ESP32)

Installation

1. Clone the repository
   ```bash
   git clone https://github.com/Manushprajwal7/Diabetes-detection-by-CNN-MLP
   cd diabetes-detection
Frontend Setup

bash
cd client
npm install
cp .env.example .env.local
# Update environment variables
Backend Setup

bash
cd ../server
npm install
cp .env.example .env
# Update environment variables
ML Server Setup

bash
cd ../model-server
pip install -r requirements.txt
ESP32 Setup

Open esp32/main/sensor_firmware.ino in Arduino IDE

Install required libraries:

WiFi.h

ArduinoWebsockets.h

Upload to ESP32 board

Running the Application
Start the backend:

bash
cd server
npm run start:dev
Start the frontend:

bash
cd ../client
npm run dev
Start the ML server:

bash
cd ../model-server
uvicorn app:app --reload
Access the application at http://localhost:3000

API Endpoints
Authentication
POST /auth/login - User login

POST /auth/register - User registration

Patients
POST /patients/onboard - Patient onboarding

GET /patients/:id/sessions - Get patient sessions

POST /predict - Submit data for prediction

WebSocket
/sensor - Real-time sensor data stream

ML Model Details
Architecture
CNN Branch: Processes pressure matrix data

2D Convolutional layers

Max pooling

Flattening layer

MLP Branch: Processes patient metadata

Dense layers with ReLU activation

Fusion: Combined via concatenation + dense layers

Training
Dataset: Plantar pressure matrices + patient metadata

Labels: Normal, Pre-Diabetic, Neuropathy

Validation: 5-fold cross-validation

Metrics: Accuracy, Precision, Recall, F1-score


Hardware Setup
Components
ESP32 DevKit V1

FSR sensors (3x)

3.3V voltage regulator

Breadboard and wiring

Pin Configuration
Sensor	ESP32 GPIO
Heel	GPIO 34
Midfoot	GPIO 35
Toes	GPIO 32
Contributing
Fork the project

Create your feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add some AmazingFeature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request

Contact
Your Name - manushprajwal555@gmail.com
Project Link: https://github.com/Manushprajwal7/Diabetes-detection-by-CNN-MLP
