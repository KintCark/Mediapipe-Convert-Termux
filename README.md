#Mediapipe safetensors converter termux (Wip)


Update:looks like you can't convert a safetensors to ckpt it won't work in the sdai full app only converting already made ckpt models work I gotta figure out how to convert diffusers to ckpt format or u can just search around huggingface for ckpt models I found a few also look on civitai they have a pickle tensor filter but most models now are safetensors so it's hard finding them but be careful don't go to sketchy websites only stay on those 2 sites.  huggingface and civitai.com 


Makesure you install UBUNTU FIRST:

1>

pkg updated && pkg upgrade -y && termux-setup-storage && pkg install wget -y && pkg install git -y && pkg install proot -y && cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh

2>

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-distutils python3-pip python3-venv python-is-python3 -y 

3>

pip install torch typing_extensions numpy Pillow requests pytorch_lightning absl-py

4>

pip install torch safetensors diffusers

5>

just put covert.py file in the termux ubuntu root folder and create 2 folders inside the root folder name one ckpt and the other output,then make sure u put the ckpt you want to convert in the ckpt folder,then copy the name of the ckpt file and paste it in code ckpt_path line so (example: change --ckpt_path /root/ckpt/model.ckpt to 
--ckpt_path /root/ckpt/openjourney.ckpt)


save the ckpt-convert.py file then just run this command:python3 convert.py --ckpt_path /root/ckpt/model.ckpt --output_path /root/output/


copy the whole command at once and paste it into termux then press enter.
