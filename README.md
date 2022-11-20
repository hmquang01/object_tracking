## <div align="center">Documentation</div>

<details>
<summary>Install</summary>

Clone repo and install [requirements.txt](https://github.com/ultralytics/yolov5/blob/master/requirements.txt) in a
[**Python>=3.7.0**](https://www.python.org/) environment, including
[**PyTorch>=1.7**](https://pytorch.org/get-started/locally/).

```bash
git clone https://github.com/hmquang01/object_tracking  # clone
cd yolov5
pip install -r requirements.txt  # install
pip install scikit-learn==0.22.2 # for running DeepSORT
```

</details>

<details>
<summary>Prepare Data</summary>
  
First, download [pretrained weights](https://drive.google.com/drive/folders/1XB6dtBYuCVZXOi2T3Z5Y139pV0pGU2OJ?usp=sharing) move to the folder. 'mars-small128.pb' is for DeepSORT and 'yolov5l.pt' & 'crowdhuman_yolov5m.pt' are for YOLOv5.
  
Then, download [videos from MOT16 training datasets](https://drive.google.com/drive/folders/1XB6dtBYuCVZXOi2T3Z5Y139pV0pGU2OJ?usp=sharing) for inference.
</details>

<details>
<summary>Inference with detect_track.py</summary>
  
`detect_track.py` runs inference on a variety of sources, and saving results to `runs/detect`.
  
```python
python detect_track.py --weights 'path to pretrained weights'  --img 640  --source 'path to MOT16 videos' --save-txt --classes 0 --line-thickness 1
```
  
</details>


<details open>
<summary>Evaluate model with evaluate_tracking.py</summary>
  
`evaluate_tracking.py` evaluates model on a some metrics, see more details [here](https://github.com/shenh10/mot_evaluation)
  
```python
python ./mot_evaluation/evaluate_tracking.py --seqmap 'path to MOT16/videos' --track 'path to runs' --gt 'path to MOT16/resized_labels'
```
  
The videos are of resolution 960×540 and the annotations are of resolution 1920×1080. So, The annotations are needed to be modified according to the video resolution.
</details>

