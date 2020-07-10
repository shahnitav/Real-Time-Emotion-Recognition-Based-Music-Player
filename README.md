# Emotion-detection

## Introduction

Uses a CNN Model of 63.2% Accuracy to recognize emotion of a human from a live feed of a webcam and then using the result from that playing music in a music player, the music playlist gets updated based on the emotion change in the human. 

This Project is an extension from the Live Emotion Detection Project by Atul Para which you can find here (https://github.com/atulapra/Emotion-detection)

## Dependencies

* Python 3, [OpenCV 3 or 4](https://opencv.org/), [Tensorflow 2](https://www.tensorflow.org/), [Python-VLC](https://pypi.org/project/python-vlc/), Tkinter
* To install the required packages, run `pip install -r requirements.txt`.

## Usage

* First, clone the repository 

* If you want to train this model or train after making changes to the model, use `python model_train.py`.

* If you want to view the predictions without training again, you can download my pre-trained model `(model.h5)` from [here](https://drive.google.com/file/d/1FUn0XNOzf-nQV7QjbBPA6-8GLoHNNgv-/view?usp=sharing) and then run `python emotions.py`.

* The folder structure is of the form:  
  Tensorflow:
  * data (folder)
  * songs (folder)
  * `model_train.py` (file)
  * `emotions.py` (file)
  * `haarcascade_frontalface_default.xml` (file)
  * `model.h5` (file)
  * `musicplayer.py` (file)
  
* To update the playlist as per your preferance, you can add them in the songs folder and categorize them in your favored emotion. 

* This implementation by default detects emotions on all faces in the webcam feed.


## Algorithm

* First, we use **haar cascade** to detect faces in each frame of the webcam feed.

* The region of image containing the face is resized to **48x48** and is passed as input to the ConvNet.

* The network outputs a list of **softmax scores** for the seven classes.

* The emotion with maximum score is displayed on the screen.


## References
* https://github.com/atulapra/Emotion-detection

* "Challenges in Representation Learning: A report on three machine learning contests." I Goodfellow, D Erhan, PL Carrier, A Courville, M Mirza, B
   Hamner, W Cukierski, Y Tang, DH Lee, Y Zhou, C Ramaiah, F Feng, R Li,  
   X Wang, D Athanasakis, J Shawe-Taylor, M Milakov, J Park, R Ionescu,
   M Popescu, C Grozea, J Bergstra, J Xie, L Romaszko, B Xu, Z Chuang, and
   Y. Bengio. arXiv 2013.
