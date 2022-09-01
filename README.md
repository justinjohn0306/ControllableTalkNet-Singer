This is a fork of SortAnon's Controllable TalkNet with the following modifications:
* New singing models have been added.
* `controllable_talknet.py` has been modified to output mel spectrograms from
  audio into the current directory during generation. These spectrograms can be
  used with my fork of
  [ddsp-singing-vocoder](https://github.com/effusiveperiscope/ddsp-singing-vocoders)
* An offline training notebook for training singing models is included: `TalkNet_Training_Offline_Singer.ipynb`
# Controllable TalkNet 
Controllable TalkNet is a web application that lets you synthesize speech, 
which mimics the pitch and pacing of an existing audio clip. It's based on [NVIDIA's implementation](https://github.com/NVIDIA/NeMo)
of TalkNet 2, with some changes to support singing synthesis and higher audio quality.

* Added Training notebook for Google Colab users

 **TalkNET Singer Model Training Notebook**: <a href="https://colab.research.google.com/github/justinjohn0306/ControllableTalkNet-Singer/blob/main/TalkNet_Training_(Singer).ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
 
  **TalkNET Singer Model Synthesis Notebook**: <a href="https://colab.research.google.com/github/justinjohn0306/ControllableTalkNet-Singer/blob/main/Controllable_TalkNet_(Singer).ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
 
 

## Requirements
* A Google account to run Colab, or...
* An NVIDIA GPU with 4+ GB of VRAM
* 10 GB of free space


### TalkNet Offline (Windows)
* [Download the setup script](https://github.com/SortAnon/ControllableTalkNet/releases/latest/download/TalkNetOffline.zip)
and extract it to a folder.
* Run setup.bat. The initial setup will take about 20 minutes.
* When it's done, run talknet.bat to start TalkNet on http://127.0.0.1:8050/. To download updates, run update.bat.

### Docker (Linux)
* Install Docker and NVIDIA Container Toolkit.
* [Download the Dockerfile.](https://raw.githubusercontent.com/SortAnon/ControllableTalkNet/main/Dockerfile)
Open a terminal, and navigate to the directory where you saved it.
* Run ```docker build -t talknet-offline .``` to build the image. Add ```sudo``` if you're not using rootless Docker.
* Run ```docker run -it --gpus all -p 8050:8050 talknet-offline``` to start TalkNet on http://127.0.0.1:8050/.
