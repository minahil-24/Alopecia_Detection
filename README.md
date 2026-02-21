YOLOv8 Alopecia Detection System (Full Stack)

Alopecia is a medical condition that causes hair loss on the scalp or other parts of the body. Early detection can help manage and treat hair loss effectively. This system allows users to upload an image or use their live camera to detect three types of alopecia, track results, and save previous detection history securely.

This full-stack web application uses a trained YOLOv8 model for accurate hair loss detection, along with a user-friendly interface for easy interaction.

Architecture

Frontend: React (Vite) – User Interface for uploading images, viewing results, and past history

Middleware: Node.js/Express (Multer) – Handles persistent image storage and acts as a proxy between frontend and AI backend

AI Core: FastAPI (Python/YOLOv8) – Processes images and predicts type of alopecia

Database: MongoDB – Stores user sessions, authentication data, and prediction history

How the App Works

User Interaction

Login or Signup with secure authentication

Upload a scalp image or use a live camera feed

Middleware (Node.js/Express)

Receives image uploads and saves them in /backend_node/uploads/<username>/

Forwards the image to the AI backend for prediction

AI Backend (FastAPI + YOLOv8)

Detects the type of alopecia or healthy scalp

Returns the prediction to the middleware

Frontend (React)

Displays prediction results with a clear UI

Stores detection in MongoDB for history tracking

Folder Structure
/yolo_system
├── /backend          # Python FastAPI (AI Inference & Auth Logic)
├── /backend_node     # Node.js Middleware (Multer Storage & Proxy)
│   └── /uploads      # Persistent image storage (<username>/<timestamp>_<file>)
├── /frontend_react   # React Frontend (Vite)
└── README.md

Setup Instructions
1. Prerequisites

Python 3.10+

Node.js 18+

MongoDB running at mongodb://localhost:27017

2. Backend AI (FastAPI)

Navigate to backend and run:

pip install -r requirements.txt
python main.py


Server will run at http://localhost:8000

3. Middleware Node.js

Navigate to backend_node and run:

npm install     # Install Node modules
npm start  # Start middleware


Middleware will run at http://localhost:3000

4. Frontend React

Navigate to frontend_react and run:

npm install    # Install Node modules
npm start   # Start frontend




5. Using the App

Login or Signup

Upload an image or use live camera feed

AI backend detects alopecia type and returns results

Results are displayed on frontend and saved in MongoDB for history tracking

Features

Detects Three Types of Alopecia – Early detection with YOLOv8 model

Secure Authentication – JWT-based login and signup

Persistent Image Storage – Images saved per user

Prediction History – View all previous detections

Intelligent Validation – Rejects blurry or low-quality images

Clean and Responsive UI – Easy-to-use interface