<h1 align="center">Social Distance Detector</h1>

<div align= "center">
  <h4>Social Distance Detection system built with OpenCV, Yolo using Deep Learning and Computer Vision concepts in order to detect social distance in real-time video streams.</h4>
</div>

![Live Demo](https://github.com/swaubhik/face-mask-detector/blob/master/Readme_images/demo.gif)

## :innocent: Motivation

In the present scenario due to Covid-19, there is no efficient social distance detection applications which are now in high demand for transportation means, densely populated areas, residential districts, large-scale manufacturers and other enterprises to ensure safety.

## :eyes: Demo

<p align="center"><img src="https://github.com/swaubhik/face-mask-detector/blob/master/Readme_images/demo.jpg" width="700" height="400"></p>
<p align="center"><img src="https://github.com/swaubhik/face-mask-detector/blob/master/Readme_images/demo_nomask1.jpg" width="700" height="400"></p>

## :warning: TechStack/framework used

- [OpenCV](https://opencv.org/)
- [Yolo](https://pjreddie.com/darknet/yolo/)
- [COCO](https://cocodataset.org/#home) -[YOLO TensorFlow implementation (darkflow)](https://github.com/thtrieu/darkflow)

## :star: Features

The following are examples of the added features. Note: You can easily on/off them in the config. options (mylib/config.py):

**_1. Real-Time alert:_**

- If selected, we send an email alert in real-time. Use case: If the total number of violations (say 10 or 30) exceeded in a store/building, we simply alert the staff.
- You can set the max. violations limit in config (`Threshold = 15`).
- This is pretty useful considering the COVID-19 scenario.

> Note: To setup the sender email, please refer the instructions inside 'mylib/mailer.py'. Setup receiver email in the config.

**_2. Threading:_**

- Multi-Threading is implemented in 'mylib/thread.py'. If you ever see a lag/delay in your real-time stream, consider using it.
- Threading removes OpenCV's internal buffer (which basically stores the new frames yet to be processed until your system processes the old frames) and thus reduces the lag/increases fps.
- If your system is not capable of simultaneously processing and outputting the result, you might see a delay in the stream. This is where threading comes into action.
- It is most suitable for solid performance on complex real-time applications. To use threading:

set `Thread = True` in the config.

**_3. People counter:_**

- If enabled, we simply count the total number of people: set `People_Counter = True` in the config.

**_4. Desired violations limits:_**

- You can also set your desired minimum and maximum violations limits. For example, `MAX_DISTANCE = 80` implies the maximum distance 2 people can be closer together is 80 pixels. If they fell under 80, we treat it as an 'abnormal' violation (yellow).
- Similarly `MIN_DISTANCE = 50` implies the minimum distance between 2 people. If they fell under 50 px (which is closer than 80), we treat it as a more 'serious' violation (red).
- Anything above 80 px is considered as a safe distance and thus, 'no' violation (green).

## :file_folder: Weights

Download the weights file from [Click to Download](https://drive.google.com/file/d/1O2zmGIIHLX8SGs24W7mjRyFKvE_CSY8n/view?usp=sharing) and place it in the 'yolo' folder.

## :key: Prerequisites

All the dependencies and required libraries are included in the file <code>requirements.txt</code> [See here](https://github.com/swaubhik/social-distance-detector/blob/master/requirements.txt)

## 🚀&nbsp; Installation

1. Clone the repo

```
$ git clone https://github.com/swaubhik/social-distance-detector.git
```

2. Change your directory to the cloned repo and create a Python virtual environment named 'test'

```
$ mkvirtualenv test
```

3. Now, run the following command in your Terminal/Command Prompt to install the libraries required

```
$ pip install -r requirements.txt
```

## :bulb: Working

1. Open terminal. Go into the cloned project directory and type the following command:

```
$python run.py -i mylib/videos/test.mp4
```

2. To run inference on an IP camera, Setup your camera url in 'mylib/config.py':

```
# Enter the ip camera url (e.g., url = 'http://127.0.0.1:8040/video')
url = ''
```

3. To detect in real-time video streams type the following command:

```
$python run.py
```

> Set url = 0 for webcam.

## :clap: And it's done!

Feel free to mail me for any doubts/query
:email: b18csel299@cit.ac.in

## :handshake: Contribution

Feel free to **file a new issue** with a respective title and description on the the [Social-Distance-Detector](https://github.com/swaubhik/social-distance-detector/issues) repository. If you already found a solution to your problem, **I would love to review your pull request**!

## :heart: Owner

Made with :heart:&nbsp; by [Swaubhik Chakraborty](https://github.com/swaubhik)

## :+1: Credits

**_Main:_**

- [https://www.pyimagesearch.com/](https://www.pyimagesearch.com/)
- [YOLOv3 Paper] (https://arxiv.org/pdf/1804.02767.pdf)
- [YOLO original paper] (https://arxiv.org/abs/1506.02640)
- [YOLO TensorFlow implementation (darkflow)] (https://github.com/thtrieu/darkflow)

**_Optional:_**

- More theory: https://www.pyimagesearch.com/2018/11/12/yolo-object-detection-with-opencv/
- Other trained model weights from official doc: https://pjreddie.com/darknet/yolo/

## :eyes: License

MIT © [Swaubhik Chakraborty](https://github.com/swaubhik/social-distance-detector/blob/master/LICENSE)
