Face Attendance Recognition System
This project implements a face recognition-based attendance system using Flask for the web framework and OpenCV for image processing. It allows users to add their faces to the system and track their attendance in real-time.

Features
Face Detection: Uses OpenCV to detect faces from the webcam feed.
Face Recognition: Identifies faces and records attendance using a trained K-Nearest Neighbors (KNN) model.
Attendance Management: Records attendance in a CSV file with name, roll number, and timestamp.
User Management: Allows adding new users and training the model with their face images.
Prerequisites
Python 3.x
Flask
OpenCV
scikit-learn
pandas
numpy
joblib
