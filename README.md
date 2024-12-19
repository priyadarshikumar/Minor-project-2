# Minor-project-2
Inspiration

OpenFace
I refer to the facenet repository of davidsandberg.
also, shanren7 repository was a great help in implementing.

Dependencies

Install the dependencies first for running the code.

Tensorflow 1.2.1 - gpu
Python 3.5
Same as requirement.txt in davidsandberg repository.

Pre-trained models

Inception_ResNet_v1 CASIA-WebFace-> 20170511-185253

Face alignment using MTCNN

You need det1.npy, det2.npy, and det3.npy in the davidsandberg repository.

How to use

First, we need align face data. So, if you need to run the script 'raw_faces_to_aligned_faces.py' first, the face data that is aligned in the 'faces/group_photos' folder will be saved.
making%20aligned%20faces.gif


Secord, we will cluster the same photos together by running the clustering_faces.py and delete the noise manually and combine the clustered faces again using combine_cluster_folder.py
deleting%20noise.gif


Third, we need to create our own classifier with the face data we created. First we will rename the folder name with the name of the person.
(In the case of me, I had a high recognition rate when I made 30 pictures for each person.) Your own classifier is a ~.pkl file that loads the previously mentioned pre-trained model ('20170511-185253.pb') and embeds the face for each person.All of these can be obtained by running 'making_classifier.py'.
making%20classifier.gif


Finally, we load our own 'my_classifier.pkl' obtained above and then open the sensor and start recognition by running labeling_faces.py
result.gif



(Note that, look carefully at the paths of files and folders in all .py)

Result


Directory Strcuture
├── 20170511-185253
│   ├── 20170511-185253.pb 
│   ├── model-20170511-185253.ckpt-80000.data-00000-of-00001
│   ├── model-20170511-185253.ckpt-80000.index
│   └── model-20170511-185253.meta
├── cls
│   └── my_classifier.pkl
├── data
│   ├── det1.npy
│   ├── det2.npy
│   └── det3.npy
├── faces
│   └── aligned photos atomatically generated from raw_photos
├── labelled_faces
│   └── folder cointaining name of that person
├── raw_faces
│   └── Add your group photos here
├── face_recognition
│   ├── __init__.py
│   ├── detect_face.py
│   ├── model_management.py
│   └── facenet.py
├── raw_faces_to_aligned_faces.py
├── making_classifier.py
├── ModelManagement.py
├── labeling_faces.py
├── detect_face.py
├── facenet.py
├── classifying_static_image.py
├── clustering_faces.py
├── combine_cluster_folder.py
