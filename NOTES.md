# Start conda venv

conda env create --file art-yolov5-p39.yml

conda activate patch-yolo

torch >=1.7.1

conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

use cmd, powershell is complicated