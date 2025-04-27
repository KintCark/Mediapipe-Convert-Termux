

u don't need to use break-system-packages anymore all you need to do is make virtual environment.



Before installing virtual environment
make sure u install ubuntu in termux first 



Install Dependencies

Since you are using CPU-only, install the necessary requirements:

pip install --no-cache-dir torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
pip install --no-cache-dir -r requirements.txt


---
python3 -m venv mediapipe-env 

source mediapipe-env/bin/activate






(Optional) Deactivate Environment

If you want to exit the virtual environment, run:

deactivate 

If running into RAM issues, consider adding swap memory in Termux.




update I fixed the ckpt convert.py it now will add missing state_dict to the ckpt. so now if u download a pickletensor u can convert it to mediapipe. thx to chatgpt 4o, look in Code Tab




if u use a mediapipe converter you will sometimes get a complete conversion but it will have 3 files missing alpha_cumprod,alpha_cumprod_prev,and beta.bin
download the required preview zip and paste the 3 files in your converted mediapipe model folder. 


Makesure you install UBUNTU FIRST:

1>

pkg updated && pkg upgrade -y && termux-setup-storage && pkg install wget -y && pkg install git -y && pkg install proot -y && cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh

2>

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-pip python3-venv python-is-python3

after you install step 2 u will get an 668 error just go step 3 and 4 install virtual environment then install step 2 again 

3>

python3 -m venv mediapipe-env

4>

source mediapipe-env/bin/activate



5>

pip install torch && pip install typing_extensions numpy pillow requests pytorch_lightning absl-py safetensors && apt-get install google-perftools && apt-get install libgoogle-perftools-dev && pip install gradio spaces



3>

AFTER you install the required files just navigate to your termux ubuntu root folder
and create 2 folders one named ckpt and other output then paste what ever sd1.5 model you want to use in the root folder then copy the name of the model open ckpt-converter.py and scroll down to line 23 i think untill u see a model name it should look like /root/YourModelName.safetensors overwrite this with the current model of choice then save also copy the 2 convert.py files to the termux ubuntu root folder,then just run this command:

python3 ckpt-convert.py && python3 convert_fixed.py --ckpt_path /root/ckpt/model.ckpt --output_path /root/output/

if u get a pickletensor file u can convert it with this code:

 python3 convert_fixed.py --ckpt_path /root/ckpt/model.ckpt --output_path /root/output/ 

just make sure u rename the ckpt to model.ckpt then place the ckpt in the ckpt folder.




everytime you convert a model the ckpt folder will have a model.ckpt file in it just delete that before converting the next model.
the output folder will have your converted mediapipe model files make sure it has the alphacum files and the beta.bin then copy all the mediapipe files to a folder and name the folder the name of the model so you know which one it is. 







