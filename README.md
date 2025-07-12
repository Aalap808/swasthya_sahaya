Face Recognition System using OpenCV & Excel
A complete beginner-friendly face recognition system using Python, OpenCV, and Excel logging. This project allows you to:

Collect face images from a webcam.

Log user details (ID, name, email) to an Excel file.

Train a face recognizer using the LBPH algorithm.

Recognize faces in real-time and label them with usernames.

 Project Structure
 https://github.com/Aalap808/swasthya_sahaya/blob/015c1fc6a8ac9de1a2b0512ff55c7dd447aa5c38/image.png


Requirements
Make sure you have Python 3.6+ installed. Then install the following dependencies:


pip install opencv-python opencv-contrib-python numpy Pillow openpyxl
. Collect Face Data
Run the following script to capture face images and log user details:


python face_data_collector.py
What it does:
Captures 30 grayscale face images per user using your webcam.

Saves them in the dataset/ folder.

Stores user ID, username, email, timestamp, and image count in user_data.xlsx.

You'll be prompted to enter:
Numeric Face ID

Username

Email address

 Press Esc or wait until 30 images are captured to stop.

2. Train the Model
Run the training script:


python train_model.py
What it does:
Loads all images from the dataset/ folder.

Detects and extracts faces using Haar Cascade.

Trains a Local Binary Patterns Histograms (LBPH) model.

Saves the model to trainer/trainer.yml.

 After training, it prints how many unique users were trained.

 3. Real-Time Face Recognition
Run the final script to recognize faces live:


python face_recognizer.py
What it does:
Loads the trainer.yml model.

Loads usernames from user_data.xlsx.

Opens the webcam and detects faces.

Predicts face ID and displays the username and confidence.

Press Esc to exit the recognition window.

 Confidence Threshold
The recognizer compares faces and returns a confidence score:

If confidence < 70, the face is labeled with the username.

Otherwise, it is labeled as "Unknown".

 Tips
Always use a consistent lighting and face angle while collecting data.

You can improve accuracy by capturing more than 30 samples and cleaning misaligned faces from the dataset.

You can extend this by saving recognition logs, integrating alerts, or building a GUI.
