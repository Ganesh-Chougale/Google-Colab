## one time setup on google drive
```bash
# Test GPU
!nvidia-smi
!python --version
```  
success
```bash
!sudo apt-get install python3.10 python3.10-venv python3.10-dev
!sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1
!sudo update-alternatives --config python3
!python --version
# Reinstall pip for Python 3.10
!curl -sS https://bootstrap.pypa.io/get-pip.py | python3.10
!python3.10 -m pip --version
```  
success
```bash
# (venv not needed in Colab, just use python3.10 directly)
# Upgrade pip + wheel inside Python 3.10
!python3.10 -m pip install --upgrade pip setuptools wheel

# Install extra deps you want
!python3.10 -m pip install fastapi
```  
```bash
# ---------- Google Drive Mount ----------
from google.colab import drive
drive.mount('/content/gdrive', force_remount=True)
```  
```bash
# ---------- Clone WebUI (skip if already exists) ----------
import os
if not os.path.exists("/content/stable-diffusion-webui"):
    !git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui /content/stable-diffusion-webui
%cd /content/stable-diffusion-webui
```  
```bash
# ---------- Download model checkpoint ----------
os.makedirs("models/Stable-diffusion", exist_ok=True)
!curl -L https://huggingface.co/CompVis/stable-diffusion-v-1-4-original/resolve/main/sd-v1-4.ckpt \
  --output "models/Stable-diffusion/sd-v1-4.ckpt"
```  
```bash
# ---------- Copy installation to Google Drive for persistence ----------
!mkdir -p /content/gdrive/MyDrive/automatic1111
!cp -a /content/stable-diffusion-webui /content/gdrive/MyDrive/automatic1111/
```  
## each time relaunch setup from google drive after one time setup
```bash
# Mount Google Drive again if starting new session
from google.colab import drive
drive.mount('/content/gdrive', force_remount=True)

# Go to persistent WebUI on Google Drive
%cd /content/gdrive/MyDrive/automatic1111/stable-diffusion-webui

# Fix Matplotlib backend for Colab
%env MPLBACKEND=Agg

# Ensure Python packages are up to date and install xformers
!python3.10 -m pip install --upgrade pip setuptools wheel
!python3.10 -m pip install xformers

# Launch WebUI with shareable link and optional authentication
!python3.10 launch.py --xformers --share --gradio-auth username:password
```  
## If upgrade the repo in the future
```bash
%cd /content/gdrive/MyDrive/automatic1111/stable-diffusion-webui
!git pull
```  