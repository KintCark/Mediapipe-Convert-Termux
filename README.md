Hey I have Great News! I fixed it! now when u Install pip not pipx u need to put --break-system-packages at the end of each pip installation packages u can look at step >2 for example the mediapipe converter works now;) 😉 


Update:if u use a mediapipe converter you will sometimes get a complete conversion but it will have 3 files missing alpha_cumprod,alpha_cumprod_prev,and beta.bin
download the required preview zip and paste the 3 files in your converted mediapipe model folder. 


Makesure you install UBUNTU FIRST:

1>

pkg updated && pkg upgrade -y && termux-setup-storage && pkg install wget -y && pkg install git -y && pkg install proot -y && cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh

2>

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-pip python3-venv python-is-python3 && pip install torch --break-system-packages && pip install typing_extensions numpy pillow requests pytorch_lightning absl-py safetensors --break-system-packages && apt-get install google-perftools && apt-get install libgoogle-perftools-dev && pip install gradio spaces --break-system-packages



3>

AFTER you install the required files just navigate to your termux ubuntu root folder
and create 2 folders one named ckpt and other output then paste what ever sd1.5 model you want to use in the root folder then copy the name of the model open ckpt-converter.py and scroll down to line 23 i think untill u see a model namevit should look like /root/YourModelName.safetensors overwrite this with the current model of choice then save also copy the 2 convert.py files to the termux ubuntu root folder,then just run this command:

python3 ckpt-convert.py && python3 convert_modified.py --ckpt_path /root/ckpt/model.ckpt --output_path /root/output/


everytime you convert a model the ckpt folder will have a model.ckpt file in it just delete that before converting the next model.
the output folder will have your converted mediapipe model files make sure it has the alphacum files and the beta.bin then copy all the mediapipe files to a folder and name the folder the name of the model so you know which one it is.













