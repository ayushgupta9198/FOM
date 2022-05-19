# FOM - First order motion model.

In this repo. you can find the source code and implementation of code towards predefined and custom images for animation.

Unzip the folder and refer the .ipynb file for code workflow and implementation of code.

Installation
We support python3. To install the dependencies run:

pip install -r requirements.txt
YAML configs
There are several configuration (config/dataset_name.yaml) files one for each dataset. See config/taichi-256.yaml to get description of each parameter.

Pre-trained checkpoint
Checkpoints can be found under following link: google-drive or yandex-disk. 

Animation Demo
To run a demo, download checkpoint and run the following command:

python demo.py  --config config/dataset_name.yaml --driving_video path/to/driving --source_image path/to/source --checkpoint path/to/checkpoint --relative --adapt_scale
The result will be stored in result.mp4.

The driving videos and source images should be cropped before it can be used in our method. To obtain some semi-automatic crop suggestions you can use python crop-video.py --inp some_youtube_video.mp4. It will generate commands for crops using ffmpeg. In order to use the script, face-alligment library is needed:

git clone https://github.com/1adrianb/face-alignment
cd face-alignment
pip install -r requirements.txt
python setup.py install

Image animation
In order to animate videos run:

CUDA_VISIBLE_DEVICES=0 python run.py --config config/dataset_name.yaml --mode animate --checkpoint path/to/checkpoint
