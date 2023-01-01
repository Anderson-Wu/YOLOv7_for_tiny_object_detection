# Object Detection on UAV images

## Group Member
* R11922029 吳泓毅
* R10922026 吳勝濬
* R10922102 林正偉

** All the operation should be in code folder **

## Dataset Download 
[Link](https://drive.google.com/file/d/1JxoA4z_GBcTmQOn2TPI80QnhtqX3rbXD/view?usp=sharing)


## Environment Setting

```bash
conda create -n yolov7 python=3.9
conda activate yolov7
pip install -r requirements.txt  
```

## Folder Structure
You need to create datasets folder by yourself
``` shell
|----code
|----datasets----DIP(extract below datasets folder)
```

## Training
``` shell
python train.py --data DIP.yaml --weights yolov7_training.pt --cfg ./cfg/training/<model>.yaml --img <img size> --epoch <epoch_num>  --freeze <freeze layers> --batch-size <batch_size>
```
&lt;model&gt;.yaml: choose model strucures which are put in cfg/training folder  
&lt;img size&gt;: training size and validation size  
&lt;epoch_num&gt;: training epoch num, 100 for img-size 640, 50 for img-size 1280  
&lt;freeze layers&gt;: fixed backbone weights before assigned layer nums, 50 for fixed backbone, 52 for fixed backbone and neck, if you don't want fixed any weight, just don't use this argument. 
&lt;batch_size&gt;: choose batch size depend on GPU



## Inference on Testing Dataset

### Testing Dataset Download
[Link](https://drive.google.com/drive/folders/1FmzosGwb6Y_HEL504mzuFrH2YdoH-WRu?usp=sharing)


### Weights Download
[Link](https://drive.google.com/drive/folders/1DzfiwvQP9NDcm7XYrOcdzrlJwJXA88bB?usp=sharing)

``` shell
python detect.py --source <test images folder> --weights <weights path>  --img <img size> 
```
&lt;test images folder&gt;: folder of test images  
&lt;weights folder&gt;: path to weights  
&lt;img size&gt;: inference size  640 or 1280 depend on training size

The results on testing images are [here](https://drive.google.com/drive/folders/16YDSfKHSoWqSJqqM8smkfSBRTungvsZa?usp=sharing)

## Acknowledgements

<details><summary> <b>Expand</b> </summary>

* [https://github.com/WongKinYiu/yolov7](https://github.com/WongKinYiu/yolov7)
* [https://github.com/AlexeyAB/darknet](https://github.com/AlexeyAB/darknet)
* [https://github.com/WongKinYiu/yolor](https://github.com/WongKinYiu/yolor)
* [https://github.com/WongKinYiu/PyTorch_YOLOv4](https://github.com/WongKinYiu/PyTorch_YOLOv4)
* [https://github.com/WongKinYiu/ScaledYOLOv4](https://github.com/WongKinYiu/ScaledYOLOv4)
* [https://github.com/Megvii-BaseDetection/YOLOX](https://github.com/Megvii-BaseDetection/YOLOX)
* [https://github.com/ultralytics/yolov3](https://github.com/ultralytics/yolov3)
* [https://github.com/ultralytics/yolov5](https://github.com/ultralytics/yolov5)
* [https://github.com/DingXiaoH/RepVGG](https://github.com/DingXiaoH/RepVGG)
* [https://github.com/JUGGHM/OREPA_CVPR2022](https://github.com/JUGGHM/OREPA_CVPR2022)
* [https://github.com/TexasInstruments/edgeai-yolov5/tree/yolo-pose](https://github.com/TexasInstruments/edgeai-yolov5/tree/yolo-pose)

</details>
