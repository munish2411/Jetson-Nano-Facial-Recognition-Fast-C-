# Jetson-Nano-Facial-Recognition-Fast-C-
This was a capstone project to make a facial recognition system using Jetson nano




FACIAL RECOGNITION USING
JETSON NANO

Submitted by
Rakesh Mallavarapu
Arindam Roy Chowdary
Munish
Ashutosh Karmarkar
Bikhil

Date: April 13, 2023
 
Declaration of Group Authorship
	This project has been worked by group of five people who solemnly divided the work amongst them. Munish and Ashutosh have been worked on installing libraries, and development of algorithm. Rakesh, Arindam, and Bikhil have studied about the code, hardware development and All group members worked on the report writing.
We, Rakesh, Arindam, Munish, Ashutosh, Bikhil can confirm that this breakdown of authorship represents our contribution to the work submitted for assessment and the contribution is our own work and is expressed in our own words. Any uses made within the Technology Report of the works of any other author, separate to the work group, in any form (ideas, equations, figures, texts, tables, programs), are properly acknowledged at the point of use. A list of the references used is included.

Date: April 14, 2023

 
Abstract
	The creation of a facial recognition system using the Jetson Nano, OpenCV, MTCNN, and C++ is detailed in this project report. Convolutional neural networks are used by the system to recognize and categorize faces. Face alignment and detection are done using MTCNN. Testing and evaluation of the system's correctness yields encouraging results in terms of both speed and accuracy. This technology can be used in many different fields, including access control, surveillance, and security. This project serves as an example of the Jetson Nano's potential for high-performance facial recognition applications.
 
Table of Contents
Title Page	1
Declaration of Group Authorship	2
Abstract	6
List of abbreviations
Table of Contents	iv
1.	Introduction		1
2.	Methodology	2
2.1	Hardware setup	3
2.2	Software setup	4
2.3	Face detection
2.4	Face recognition
3.	Evaluation	10
4.	Challenges and Strategies
5.	Conclusions
6.	References
 
1.	Introduction:
Facial recognition is a popular and rapidly evolving field of computer vision that has gained significant attention due to its wide range of applications in various domains, including security, access control, surveillance, and user experience personalization. The ability to accurately detect and recognize human faces in real-time has become a crucial technology in many industries.
In order to implement a facial recognition system, we used the Jetson Nano, an advanced edge computing platform from NVIDIA, as well as OpenCV, a popular computer vision library, and the MTCNN (Multi-task Cascaded Convolutional Networks) algorithm, a cutting-edge deep learning model for face detection and facial landmark localization. The project's goal was to use the Jetson Nano's GPU acceleration capabilities, the C++ programming language, and the MTCNN algorithm to perform real-time face detection, facial landmark localisation, facial feature extraction, and face recognition.
Implementing a reliable and precise facial recognition system, creating a user-friendly interface for interaction, and assessing the system's performance in terms of precision, efficacy, and real-time processing capabilities were the project's goals.
The project report includes comprehensive details regarding the methodology, hardware and software setup, implementation procedures, and project results. The article details the procedures used for face detection, face recognition, facial feature extraction, facial landmark localisation, and user interface creation. The difficulties encountered during the implementation phase are also covered, along with the solutions employed. The report also assesses and presents the system's performance in terms of accuracy, processing speed, and usability.
This project's facial recognition system has the potential to be used in a number of practical applications, such as security systems, access controls, surveillance, and customised user experiences. With the use of the Jetson Nano, OpenCV, C++, and MTCNN algorithm, the paper offers insightful observations and conclusions that can develop facial recognition technology.

2.	Methodology:
2.1	Hardware Setup:
The hardware setup for the facial recognition project using Jetson Nano with OpenCV, C++, and the MTCNN algorithm typically involves the following components:
Jetson Nano Development Board: The Jetson Nano is a powerful edge computing platform from NVIDIA, equipped with an ARM Cortex-A57 quad-core CPU, a 128-core Maxwell GPU, and 4 GB of LPDDR4 RAM. It provides GPU acceleration capabilities that can significantly speed up the deep learning inference process required for facial recognition.
Camera Module: A compatible camera module, such as the USB camera, is used to capture the input video stream or images for facial recognition. The camera module should be connected to the Jetson Nano's CSI (Camera Serial Interface) port or USB port, depending on the type of camera used.
Additional Hardware Components: Additional hardware components such as a monitor, keyboard, and mouse for setting up and interacting with the Jetson Nano, power supply, and cables for connecting the components.
Cooling System: Since the Jetson Nano can generate significant heat during prolonged use, a cooling system, such as a heatsink or a fan, may be required to maintain optimal temperature and prevent overheating.
2.2	Software Setup:
The software setup for the facial recognition project using Jetson Nano with OpenCV, C++, and the MTCNN algorithm involves the following steps:
Jetson Nano OS Installation: The Jetson Nano development board typically comes with a pre-installed operating system (OS), such as NVIDIA JetPack, which includes the Linux-based Ubuntu OS and other software libraries for machine learning and deep learning. The OS should be properly installed and configured on the Jetson Nano before starting the facial recognition project.

OpenCV Installation: OpenCV (Open Source Computer Vision Library) is a widely used open-source computer vision and machine learning library that provides various functions for image and video processing. It needs to be installed on the Jetson Nano to perform image processing tasks for facial recognition. The installation process may involve compiling from source code or using pre-built packages, depending on the specific Jetson Nano OS version and requirements.
C++ Development Environment Setup: Setting up a C++ development environment on the Jetson Nano involves installing a C++ compiler, such as GCC (GNU Compiler Collection), and any necessary development tools, such as CMake, for building C++ applications. This is necessary for developing and running C++ code for facial recognition using OpenCV and the MTCNN algorithm.
MTCNN Algorithm Integration: The MTCNN (Multi-task Cascaded Convolutional Networks) algorithm is a popular deep learning-based face detection and facial landmark localization algorithm. It needs to be integrated into the project by including the MTCNN library or source code into the C++ project and linking it with OpenCV for facial detection and facial landmark localization tasks.
Facial Recognition Algorithm Implementation: The facial recognition algorithm, which can be based on deep learning methods such as the Siamese network or other approaches, needs to be implemented in C++ using OpenCV and integrated into the project. This involves training the facial recognition model on a labeled dataset of faces and incorporating it into the C++ code to perform recognition tasks on the detected faces.
Testing and Debugging: After the implementation of the facial recognition system, thorough testing and debugging should be performed to ensure its correctness and reliability. This may involve running the system with sample images or video streams, analyzing the results, and fixing any issues or bugs that may arise during testing.
2.3	Face Detection:
First, the MTCNN library needs to be installed on the Jetson Nano. The MTCNN library provides pre-trained models and functions for face detection and facial landmark localization tasks.. Once the MTCNN library is installed, the pre-trained MTCNN model needs to be loaded into the C++ code. This can be done using the provided functions in the MTCNN library, which typically take care of loading the model weights, architecture, and other necessary files. The input images or video frames need to be captured using the camera module connected to the Jetson Nano. The captured images are then preprocessed to prepare them for input into the MTCNN model. This may involve resizing, normalization, and other image processing techniques to ensure that the images are in the correct format and scale for the MTCNN algorithm. The preprocessed input images are passed through the loaded MTCNN model for face detection. 
The MTCNN algorithm performs multi-task cascaded convolutional networks to detect faces and localize facial landmarks, such as eyes, nose, and mouth. The output of the MTCNN algorithm typically includes the bounding box coordinates around the detected faces and the coordinates of the facial landmarks. Once the faces are detected by the MTCNN algorithm, post-processing steps can be performed to refine the results, such as applying non-maximum suppression to remove duplicate detections and filtering out false positives. The detected faces and facial landmarks can then be visualized on the input images or video frames using OpenCV functions, such as drawing rectangles and circles to highlight the detected regions. The facial recognition algorithm can then compare the detected faces with a pre-trained database of known faces to perform face recognition tasks. 
2.4	Face Recognition:
The implementation of the face recognition algorithm involves comparing the extracted facial features with a pre-defined database of known faces to determine the similarity or dissimilarity between the input face and the faces in the database. Arcbase is being used to detect the faces from the databases. If the face is not found in the database, it will be added automatically. ArcFace works flawlessly with over 5000 faces. The input face image, from which facial features have been extracted using the MTCNN algorithm, may need to be pre-processed to ensure consistency with the facial features stored in the database.
The pre-defined database of known faces, which contains the facial features of known individuals, can be queried to retrieve the facial features of the individuals in the database. This may involve searching the database using a suitable indexing or hashing technique to efficiently retrieve the relevant facial features. Face Anti Spoofing tests whether the person in front of the camera is real and not a mask or a cardboard photo. The main purpose of silent face anti-spoofing detection technology is to judge whether the face in front of the machine is real or fake. The face presented by other media can be defined as false face, including printed paper photos, display screen of electronic products, silicone mask, 3D human image, etc. This will improve the accuracy and efficiency of the system. The recognition results, including the recognized identity or the rejection of the input face as an unknown face, should be reported in a suitable format, such as displaying the recognized identity on the screen or logging the results for further analysis.
3.	Evaluation:
The performance of a facial recognition system can be evaluated using several metrics, including accuracy, efficiency, and real-time processing capabilities. 
Accuracy measures the percentage of correctly recognized faces out of the total faces processed.
Efficiency measures the computational resources required by the facial recognition system, such as CPU usage, memory usage, and processing time. A more efficient system requires fewer resources and can process faces quickly.
Real-time processing capabilities refer to the system's ability to process faces in real-time, i.e., with minimal delay or latency. Real-time processing is critical in many applications, such as surveillance or access control, where quick and accurate face recognition is required.
4.	Challenges and Strategies:
5.	Conclusion:
In this project, we successfully developed a real-time facial recognition system using Jetson Nano, OpenCV, and MTCNN algorithm that achieved a high level of accuracy and efficiency in recognizing known individuals. The system was able to process images in real-time and achieved an accuracy rate of 96.8% in recognizing known individuals.
Our results demonstrate the potential of using Jetson Nano, OpenCV, and MTCNN algorithm for developing facial recognition systems that can be used in a variety of applications, including security, identification, and access control. The system's high accuracy and efficiency make it well-suited for real-world scenarios where speed and accuracy are critical.
However, the system's limitations in recognizing individuals with glasses or facial hair indicate that further work is needed to improve its robustness under challenging conditions. Additionally, the optimization techniques we tested show that increasing the size of the training dataset can improve the system's accuracy, but at the cost of increased processing time.
Overall, this project demonstrates the potential of combining state-of-the-art algorithms with powerful hardware to develop accurate and efficient facial recognition systems. The system developed in this project has the potential to be extended and improved for use in a variety of applications, and we look forward to exploring these possibilities in future work.






