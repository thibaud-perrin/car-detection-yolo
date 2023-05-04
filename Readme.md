# YOLOV2 Car Detection Project

<div align="center" float="left">
    <img src="./out/car_detection.gif" width="50%" />
</div>

This project applies YOLOV2 for car detection using the Keras version from [allanzelener/YAD2K](https://github.com/allanzelener/YAD2K). The goal is to use YOLO in the field of an autonomous driving applications. The car detection is performed on a dataset provided by [drive.ai](https://www.drive.ai/).

## Requirements
- numpy
- jupyterlab
- matplotlib
- imageio
- imageio[ffmpeg]
- scipy
- Pillow
- ipython
- nodejs-bin
- jupyter_contrib_nbextensions
- tensorflow
- pandas
The requirements are also listed in requirements.txt.


## Installation
1. Install the required packages:  
These packages can be installed by running the following command:
```bash
# Load pipenv env
pipenv shell
# Install packages
pipenv install --requirements "requirements.txt"
# Install ipython in jupyter lab
jupyter labextension install @jupyter-widgets/jupyterlab-manager
jupyter labextension install jupyter-matplotlib
# Fixe jupyter_nbextensions_configurator error
jupyter nbextensions_configurator enable --user
```
2. Load weights:  
download `yolo.weights` and `yolov2.cfg` and put them in `model_data`, and then, transform them to `yolo.h5`
```bash
wget http://pjreddie.com/media/files/yolo.weights
wget https://raw.githubusercontent.com/pjreddie/darknet/master/cfg/yolov2.cfg
python yad2k.py model_data\yolov2.cfg model_data/yolo.weights model_data/yolo.h5
```

3. Launch JupyterLab:
```
jupyter-lab
```
4. Open the car_detection.ipynb notebook and run the cells to perform car detection on the provided dataset.


## Project Structure
The project has the following tree structure:

```
.
├── font
│   └── FiraMono-Medium.otf
├── images
│   ├── 001.jpg
│   ├── ...
│   └── 0120.jpg
├── model_data
│   ├── _anchors.txt
│   ├── coco_classes.txt
│   ├── pascal_classes.txt
│   ├── saved_model.pb
│   └── yolo_anchors.txt
├── yad2k
│   ├── ...
│   └── ...
├── yad2k.py
├── Pipfile
├── Pipfile.lock
├── car_detection.ipynb
├── README.md
└── LICENSE.md
```

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.