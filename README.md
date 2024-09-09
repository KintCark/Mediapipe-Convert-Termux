#Mediapipe safetensors converter termux 
LCM and Hyper SD1.5 Models Work!

Update:if u use a mediapipe converter you will sometimes get a complete conversion but it will have 3 files missing alpha_cumprod,alpha_cumprod_prev,and beta.bin
download the required preview zip and paste the 3 files in your converted mediapipe model folder. 


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

first Navigate to termux ubuntu root folder.

next create 2 folders name one ckpt and the other output.

then copy the ckpt-convert.py and convert.py files to the ubuntu root folder.

next download any safetensors model and copy it to your ubuntu root folder,I like to use stargon browser Cuzco u can pick where u wanna download the file so I just save it in the ubuntu root folder.

next open the ckpt-convert.py and scroll down untill u see and safetensors model name it should be goddess etc safetensors copy the name of your downloaded safetensors and overwrite the name of the current model in the path.do not erase the root name just overwrite the model. then save. it with an text editor I use quick text editor pro it's 👍. 

now run this command 

python3 ckpt-convert.py && python3 convert.py --ckpt_path /root/ckpt/model.ckpt --output_path /root/output/

paste the whole thing in termux and the ull convert the safetensors to mediapipe then just download sdai full version select mediapipe local diffusion turn on load local model allow permission and then if u don't have SDAI folder in downloads just create it and then create model folder inside SDAI folder then go to ubuntu root open output copy all those files to SDAI/model folder. 

now some conversions don't create the preview files like I mentioned above so just download them and paste them in the model folder if you don't your app will crash when load image.


enjoy:)
