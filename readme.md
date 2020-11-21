## Training Object Detection Classifier for Mask Recognition using TensorFlow

It is created using TensorFlow's Object Detection API to train object detection classifier for face mask detection in COVID-19. <br>
The model has been trained on <b>Google Colab with GPU</b> and the runtime was approximately <b>2-3 hours.</b><br><br>
TensorFlow already provides several object detection models (pre-trained classifiers with specific neural network architectures) in its [model zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf1_detection_zoo.md). I re-trained my model on <b>Faster-RCNN-Inception-V2-COCO</b> since this project works with images and I preferred to go for higher accuracy. The SDD-MobileNet model seems better for faster fps in videos but underperforms when it comes to accuracy.<br><br>

<b>The model detects the users with typically 3 categories: </b>

|S.No.|Label|Color|
|:--:|:---:|:---:|
| 1  |with_mask             | ![#82FF02](https://via.placeholder.com/15/82FF02/000000?text=+) |
| 2  | without_mask         | ![#01FEFC](https://via.placeholder.com/15/01FEFC/000000?text=+) | 
| 3  | mask_weared_incorrect| ![#85FDCF](https://via.placeholder.com/15/85FDCF/000000?text=+) | <br>

## Outputs

<img src="images_readme/image1.jpg" width="42.25%"> <img src="images_readme/image3.jpg" width="52.25%"> 

<img src="images_readme/image8.jpg" width="95%"> 

<img src="images_readme/image4.jpg" width="36%"> <img src="images_readme/image10.jpg" width="58.5%"> 

<img src="images_readme/image5.jpg" width="59.5%"> <img src="images_readme/image7.jpg" width="35%" height="60%">

<img src="images_readme/image6.jpg" width="42.5%"> <img src="images_readme/image9.jpg" width="52%">

<img src="images_readme/image2.jpg" width="80%">

<hr>

## <i>How to test your own images ?</i>
<b>1. Download my repository to a location you remember. (*Use git clone or Download ZIP*) </b> <br><br>
<b>2. Setup a virtual environment. </b> (*I have used anaconda for this project with python 3.7 to maintain compatibility with tensorflow*) <br><br>
&emsp;`conda create -n mask_detection python=3.7`<br>
&emsp;`conda activate mask_detection`<br>

<b>3. Install libraries in virtual environment. </b>(Use either *a* or *b*)<br><br>
&emsp;`conda activate mask_detection`<br>
&emsp;`cd Mask-Detection`<br><br>
&emsp; <b>a. Use the commands below : </b><b>(*DO NOT use TensorFlow 2.x</b> as it has compatibilty issues with some existing libraries!*)<br>
&emsp;&emsp;`pip install TensorFlow==1.15 lxml pillow matplotlib jupyter contextlib2 cython tf_slim` <br>
&emsp;&emsp;`pip install "git+https://github.com/philferriere/cocoapi.git#egg=pycocotools&subdirectory=PythonAPI"` <br><br>
&emsp; <b>b. Install using requirements.txt:<br></b>
&emsp;&emsp;`pip install -r requirements.txt`<br>

<b>4. Launch Jupyter Notebook by typing : `jupyter notebook` <br><br></b>
<b>5. Open Mask_Detection.ipynb. </b><br><br>
&emsp;i. You need to put the absolute path of <b>Mask_Detection</b> folder in `INITIAL_DIR=''` variable<br><br>
&emsp;ii. Put the images you want to try inside the <b>test_images</b> folder inside <b>Mask_Detection</b><br>
&emsp;*Currently, the absolute path is for INITIAL_DIR as `C:/Users/Raghu/Mask-Detection` which is where I saved the repository*<br><br>
<b>6. The outputs will be shown or saved to the Outputs folder.</b>
