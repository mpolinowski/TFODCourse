# Tensorflow Object Detection Walkthrough

This set of Notebooks provides a complete set of code to be able to train and leverage your own custom object 
detection model using the Tensorflow Object Detection API.


![Tensorflow Object Detection Walkthrough](https://i.imgur.com/H3tUyKM.png)

## Steps

* __Step 1__: Clone this repository: https://github.com/mpolinowski/TFODCourse
* __Step 2__: Create a new virtual environment 

```bash
python -m venv tfod
```

* __Step 3__: Activate your virtual environment

```bash
source tfod/bin/activate # Linux
.\tfod\Scripts\activate # Windows 
```

* __Step 4__: Install dependencies and add virtual environment to the Python Kernel

```bash
python -m pip install --upgrade pip
pip install ipykernel
python -m ipykernel install --user --name=tfodj
```

* __Step 5__: Collect images using the Notebook <a href="https://github.com/mpolinowski/TFODCourse/blob/main/collecting_training_data.ipynb">collecting_training_data.ipynb</a> - ensure you change the kernel to the virtual environment as shown below

![Tensorflow Object Detection Walkthrough](https://i.imgur.com/8yac6Xl.png)

* __Step 6__: Manually divide collected images into two folders train and test. So now all folders and annotations should be split between the following two folders.

```bash
mkdir -p TFODCourse/Tensorflow/workspace/images/{train,test}
```

* __Step 7__: Begin training process by opening <a href="https://github.com/mpolinowski/TFODCourse/blob/main/training_the_model.ipynb">2. Training and Detection.ipynb</a>, this notebook will walk you through installing Tensorflow Object Detection, making detections, saving and exporting your model. 

* __Step 8__: During this process the Notebook will install Tensorflow Object Detection. You should ideally receive a notification indicating that the API has installed successfully at Step 8 with the last line stating OK.  

![Tensorflow Object Detection Walkthrough](https://i.imgur.com/FSQFo16.png)

If not, resolve installation errors by referring to the [Error_Guide.md](https://github.com/mpolinowski/TFODCourse/blob/main/Error_Guide.md) in this folder.

* __Step 9__: Once you get to step 6. Train the model, inside of the notebook, you may choose to train the model from within the notebook. I have noticed however that training inside of a separate terminal on a Windows machine you're able to display live loss metrics. 

![Tensorflow Object Detection Walkthrough](https://i.imgur.com/K0wLO57.png)

* __Step 10__: You can optionally evaluate your model inside of Tensorboard. Once the model has been trained and you have run the evaluation command under Step 7. Navigate to the evaluation folder for your trained model e.g.

```bash
cd Tensorlfow/workspace/models/my_ssd_mobnet/eval
```
 

and open Tensorboard with the following command

```bash
tensorboard --logdir=.
```

Tensorboard will be accessible through your browser and you will be able to see metrics including mAP - mean Average Precision, and Recall.


* __Step 11__: Run object detection on images and live RTSP streams - [run-object-detection.ipynb](https://github.com/mpolinowski/TFODCourse/blob/main/run-object-detection.ipynb)


* __Step 12__: Freeze your graph and convert / export to [Tensorflow.js](https://www.tensorflow.org/js) and [Tensorflow Lite](https://www.tensorflow.org/lite/) - [run-object-detection.ipynb](https://github.com/mpolinowski/TFODCourse/blob/main/freeze-and-export-models.ipynb)