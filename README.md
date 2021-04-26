# human-pose-estimation-opencv
Perform Human Pose Estimation in OpenCV Using OpenPose MobileNet

您好，我们是安坐sity团队，我们的产品基于OpenCv来视觉识别人体坐姿。我们期待以这种开源的方式和用户达到需求的交互。
Hello, we are the Anzai sity team. Our product is based on OpenCv to visually recognize the human sitting posture. 
We look forward to interacting with users to meet their needs in this open source way.

若您有脊椎疼痛，坐姿不当等问题，您可以使用我们的产品。
您可以自己编辑提醒方式，您可以任意修改代码，但是请您将您的反馈提交。
If you have spinal pain, improper sitting posture and other problems, you can use our products.
You can edit the reminder method yourself, and you can modify the code arbitrarily, but please submit your feedback.

我们将会收集您的坐姿识别结果数据，我们将基于这个数据来优化我们的模型，同时将针对您的数据定制运动，您将能够得到定制的运动
We will collect the result data of your sitting posture recognition. We will optimize our model based on this data. 
At the same time, we will customize the exercise based on your data, and you will be able to get customized exercises.




# How to use

- Test with webcam

```
python openpose.py
```

- Test with image
```
python openpose.py --input image.jpg
```

- Use `--thr` to increase confidence threshold

```
python openpose.py --input image.jpg --thr 0.5
```

# Notes:
- I modified the [OpenCV DNN Example](https://github.com/opencv/opencv/blob/master/samples/dnn/openpose.py) to use the `Tensorflow MobileNet Model`, which is provided by [ildoonet/tf-pose-estimation](https://github.com/ildoonet/tf-pose-estimation/tree/master/models/graph/mobilenet_thin), instead of `Caffe Model` from CMU OpenPose. The original `openpose.py` from `OpenCV example` only uses `Caffe Model` which is more than 200MB while the `Mobilenet` is only 7MB.
- Basically, we need to change the `cv.dnn.blobFromImage` and use `out = out[:, :19, :, :]` to get only the first 19 rows in the `out` variable.
