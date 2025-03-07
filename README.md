<h1 align="center">Watermark Detection System</h1>

<p>This repository contains the code and data for a Watermark Detection System. This system is designed to detect the presence of watermarks in images using different image processing techniques and machine learning models. The following methods are implemented:</p>

<ul>
    <li><a href="#contour-detection-with-canny-edge-detector">Contour Detection with Canny Edge Detector</a></li>
    <li><a href="#simple-cnn-with-tensorflow">WaterMark-Detection-Using-tensorflow</a></li>
    <li><a href="#resnet-architecture">ResNet Architecture</a></li>
    <li><a href="#vgg16-architecture">VGG16 Architecture</a></li>
</ul>

<h2 id="introduction">Introduction</h2>
<p>Watermark detection is essential for verifying the authenticity and ownership of digital images. In this project, various methods are used to detect watermarks in images to compare their effectiveness. The approaches include traditional image processing techniques and advanced deep learning models.</p>

<h2 id="dataset">Dataset</h2>
<p>The dataset used for this project includes images with and without watermarks. You can download the dataset from the following link:</p>
<p><a href="https://drive.google.com/file/d/1JWpW6JTdV__L-j18QU3wgGrcIdguHl8l/view">Google Drive - Watermark Dataset</a></p>



### Download and Extract Dataset

To download and extract the dataset, use the following Python script:

```python
import gdown
import zipfile
import os

base_dir = '/content/drive/MyDrive/dk-dataset'
if not os.path.exists(base_dir):
    os.makedirs(base_dir)

zip_file_path = os.path.join(base_dir, 'dk-dataset.zip')

file_id = '1JWpW6JTdV__L-j18QU3wgGrcIdguHl8l'
download_url = f'https://drive.google.com/uc?id={file_id}'

!pip install gdown
gdown.download(download_url, zip_file_path, quiet=False)

with zipfile.ZipFile(zip_file_path, 'r') as zf:
    zf.extractall(base_dir)
```
    
<h2 id="installation">Installation</h2>
<p>To run the code for the different methods, you will need to install the following dependencies:</p>
<ul>
    <li>Python 3.x</li>
    <li>OpenCV</li>
    <li>NumPy</li>
    <li>TensorFlow</li>
</ul>
<p>Install the required packages using <code>pip</code>:</p>
<pre><code>pip install opencv-python numpy tensorflow</code></pre>

<h2 id="project-structure">Project Structure</h2>
<p>The repository is organized as follows:</p>
<pre><code>WaterMark-Detection-System/
│
├── data/
│   └── sample_image.jpg       # Example image file
│
├── src/
│   ├── contour_detection.py   # Python script for watermark detection using contours and Canny edge detector
│   ├── simple_cnn.py          # Python script for watermark detection using a simple CNN with TensorFlow
│   ├── resnet_model.py        # Python script for watermark detection using ResNet architecture
│   ├── vgg16_model.py         # Python script for watermark detection using VGG16 architecture
│
├── results/
│   └── detected_watermark.png # Output image with detected watermark
│
├── LICENSE
└── README.md
</code></pre>

<h3>Cloning the Repository</h3>
<p>To get started with this project, clone the repository using the following command:</p>
<pre><code>git clone https://github.com/safwannasir49/WaterMark-Detection-System.git
cd WaterMark-Detection-System
</code></pre>

<h2 id="contour-detection-with-canny-edge-detector">Contour Detection with Canny Edge Detector</h2>
<p>This method uses traditional image processing techniques to detect watermarks. It involves edge detection and contour analysis to identify potential watermarked regions in the images.</p>
<p>To use this method, run the <code>contour_detection.py</code> script found in the <code>src</code> directory. This script performs the following tasks:</p>
<ul>
    <li>Loads the image in grayscale.</li>
    <li>Applies the Canny edge detector to highlight edges in the image.</li>
    <li>Finds contours in the edge-detected image.</li>
    <li>Draws the contours on the original image and saves the result.</li>
</ul>

<h2 id="simple-cnn-with-tensorflow">WaterMark-Detection-Using-tensorflow</h2>
<p>This method uses a simple Convolutional Neural Network (CNN) built from scratch using TensorFlow to detect watermarks. The CNN architecture includes convolutional layers, activation functions, and pooling layers.</p>
<p>To use this method, run the <code>simple_cnn.py</code> script found in the <code>src</code> directory. This script performs the following tasks:</p>
<ul>
    <li>Loads and preprocesses images from the dataset.</li>
    <li>Defines and trains a CNN model to classify images as watermarked or non-watermarked.</li>
    <li>Evaluates the model's performance on a validation set.</li>
</ul>

<h2 id="resnet-architecture">ResNet Architecture</h2>
<p>This method uses the ResNet architecture for watermark detection. ResNet, or Residual Networks, are deep learning models that use residual connections to improve training.</p>
<p>To use this method, run the <code>resnet_model.py</code> script found in the <code>src</code> directory. This script performs the following tasks:</p>
<ul>
    <li>Loads and preprocesses images from the dataset.</li>
    <li>Defines and trains a ResNet model for watermark detection.</li>
    <li>Evaluates the model's performance on a validation set.</li>
</ul>

<h2 id="vgg16-architecture">VGG16 Architecture</h2>
<p>This method uses the VGG16 architecture for watermark detection. VGG16 is a deep convolutional neural network model known for its simplicity and effectiveness in image classification tasks.</p>
<p>To use this method, run the <code>vgg16_model.py</code> script found in the <code>src</code> directory. This script performs the following tasks:</p>
<ul>
    <li>Loads and preprocesses images from the dataset.</li>
    <li>Defines and trains a VGG16 model for watermark detection.</li>
    <li>Evaluates the model's performance on a validation set.</li>
</ul>

<h2 id="key-results">Key Results</h2>
<p>After running the watermark detection algorithms, the system will generate results indicating the presence of watermarks in the images. The results are saved in the <code>results</code> directory.</p>
<!--<h3>Detected Watermark</h3>
<p>This image shows the detected watermark regions highlighted in the original image.</p>
<img src="results/detected_watermark.png" alt="Detected Watermark">
-->

<h2 id="future-work">Future Work</h2>
<p>Future enhancements to this project could include:</p>
<ul>
    <li><strong>Improved Detection Algorithms</strong>: Implement more sophisticated algorithms for better accuracy.</li>
    <li><strong>Color Image Support</strong>: Extend the system to handle color images in addition to grayscale images.</li>
    <li><strong>Robustness</strong>: Increase the robustness of the system to handle various types of watermarks and image qualities.</li>
    <li><strong>Automated Testing</strong>: Develop automated testing scripts to evaluate the effectiveness of different models and algorithms.</li>
    <li><strong>User Interface</strong>: Develop a user-friendly interface for easier use of the system.</li>
</ul>

<h2 id="contributing">Contributing</h2>
<p>Contributions are welcome! Please open an issue or submit a pull request for any improvements or suggestions.</p>

<h2 id="license">License</h2>
<p>This project is licensed under the MIT License - see the <a href="LICENSE">LICENSE</a> file for details.</p>

<h2 id="conclusion">Conclusion</h2>
<p>This project demonstrates a basic system for detecting watermarks in images using various techniques. By applying edge detection, contour analysis, and advanced neural network architectures, the system can identify potential watermarked regions. Future work can enhance the system's accuracy and usability, making it a valuable tool for digital image verification and copyright protection.</p>
<br>
<hr/>


<br><br>

<h3 align="center">Connect with me:</h3>
<p align="center">
       <a href="mailto:safwannasir49@gmail.com" target="blank">
        <img align="center" src="https://www.svgrepo.com/show/484206/mail.svg" alt="safwannasir49@gmail.com" height="30" width="40" />
    </a>
    <a href="https://twitter.com/SafwanNasir49" target="blank">
        <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/twitter.svg" alt="safwannasir" height="30" width="40" />
    </a>
    <a href="https://linkedin.com/in/safwan-nasir-955745219" target="blank">
        <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="safwa_nasir" height="30" width="40" />
    </a>
    <a href="https://github.com/safwannasir49" target="blank">
        <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/github.svg" alt="safwannasir49" height="30" width="40" />
    </a>
</p>
