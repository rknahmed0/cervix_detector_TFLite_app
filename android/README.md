## Info
This repo provides an Android demo app able to detect the cervix from images and in live detection mode.

## Usage

### Ignore steps 1 and 2 and move to step 3 for testing out the already provided models form the assets folder

### 1. Clone this repo for Android app
```
git clone https://github.com/rknahmed0/yolov5.git yolov5_android_tflite
```

### 2. Put TFLite models in `assets` folder of Android project (4 versions: fp32, fp16, 640_int8, 320_int8 tflite models already provided in assets folder), and change 
- `inputSize` to `--img`
- `output_width` according to new/old `inputSize` ratio
- `anchors` to `m.anchor_grid` as https://github.com/ultralytics/yolov5/pull/1127#issuecomment-714651073 
- `labelFilename` according to the classes of the model

#### all above changes in:
https://github.com/rknahmed0/cervix_detector_TFLite_app/blob/main/android/app/src/main/java/org/tensorflow/lite/examples/detection/tflite/DetectorFactory.java#L19-L48. 

Then run the program in Android Studio.

### 3. Change lines 117, 119, 121 on MainActivity.java to account for the model that is being used to run inference on preset images

https://github.com/rknahmed0/cervix_detector_TFLite_app/blob/main/android/app/src/main/java/org/tensorflow/lite/examples/detection/MainActivity.java#L117-L121. 

For further questions, please ask in https://github.com/ultralytics/yolov5/pull/1127
