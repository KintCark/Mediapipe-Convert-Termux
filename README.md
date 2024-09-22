

#Mediapipe safetensors converter termux 
LCM and Hyper SD1.5 Models Work!
Bf16 is now Supported!!


Update:if u use a mediapipe converter you will sometimes get a complete conversion but it will have 3 files missing alpha_cumprod,alpha_cumprod_prev,and beta.bin
download the required preview zip and paste the 3 files in your converted mediapipe model folder. 


Makesure you install UBUNTU FIRST:

1>

pkg updated && pkg upgrade -y && termux-setup-storage && pkg install wget -y && pkg install git -y && pkg install proot -y && cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh

2>

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-distutils python3-pip python3-venv python-is-python3 -y && 
pip install torch typing_extensions numpy Pillow requests pytorch_lightning absl-py && pip install torch safetensors



3>

AFTER you install the required files just navigate to your termux ubuntu root folder
and create 2 folders one named ckpt and other output then paste what ever sd1.5 model you want to use in the root folder then just run this command:
python3 ckpt-convert.py && python3 convert_modified.py --ckpt_path /root/ckpt/model.ckpt --output_path /root/output/

















