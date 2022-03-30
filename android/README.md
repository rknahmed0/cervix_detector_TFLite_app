## Info
This repo provides an Android demo app able to detect the cervix from images and in live detection mode.

## Usage

### 1. Clone this repo for Android app
```
git clone https://github.com/rknahmed0/yolov5.git yolov5_android_tflite
```

### 2. Put TFLite models in `assets` folder of Android project (2 versions, fp32 and fp16, of tflite model already provided in assets folder), and change 
- `inputSize` to `--img`
- `output_width` according to new/old `inputSize` ratio
- `anchors` to `m.anchor_grid` as https://github.com/ultralytics/yolov5/pull/1127#issuecomment-714651073 
- `labelFilename` according to the classes of the model

#### all above changes in:
https://github.com/rknahmed0/yolov5/blob/tf-android/android/app/src/main/java/org/tensorflow/lite/examples/detection/tflite/DetectorFactory.java#L19-L48. 

Then run the program in Android Studio.

For further questions, please ask in https://github.com/ultralytics/yolov5/pull/1127
