!curl -Lo memfix.zip https://github.com/nolanaatama/microsoftexcel/raw/main/memfix.zip
!unzip /content/memfix.zip
!apt install -qq libunwind8-dev
!apt install -qq libcairo2-dev pkg-config python3-dev
!dpkg -i *.deb
%env LD_PRELOAD=libtcmalloc.so
!rm *
!pip install torch==2.0.0+cu118 torchvision==0.15.1+cu118 torchaudio==2.0.1+cu118 torchtext==0.15.1 torchdata==0.6.0 --extra-index-url https://download.pytorch.org/whl/cu118 -U
!pip install xformers==0.0.19 triton==2.0.0 -U
!curl -Lo microsoftexcel.zip https://huggingface.co/nolanaatama/colab/resolve/main/microsoftexcel.zip
!unzip /content/microsoftexcel.zip
!git clone https://github.com/nolanaatama/microsoftexcel-tunnels /content/microsoftexcel/extensions/microsoftexcel-tunnels
!git clone https://github.com/nolanaatama/microsoftexcel-controlnet /content/microsoftexcel/extensions/microsoftexcel-controlnet
!git clone https://github.com/fkunn1326/openpose-editor /content/microsoftexcel/extensions/openpose-editor
!git clone https://github.com/hnmr293/posex /content/microsoftexcel/extensions/posex
!git clone https://github.com/nolanaatama/a1111-microsoftexcel-tagcomplete /content/microsoftexcel/extensions/a1111-microsoftexcel-tagcomplete
!git clone https://github.com/nolanaatama/microsoftexcel-supermerger /content/microsoftexcel/extensions/microsoftexcel-supermerger
!git clone https://github.com/Coyote-A/ultimate-upscale-for-automatic1111 /content/microsoftexcel/extensions/ultimate-upscale-for-automatic1111
!git clone https://github.com/nolanaatama/a1111-microsoftexcel-locon /content/microsoftexcel/extensions/a1111-microsoftexcel-locon
!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-images-browser.zip https://huggingface.co/nolanaatama/colab/resolve/main/microsoftexcel-images-browser.zip
%cd /content/microsoftexcel/extensions
!unzip /content/microsoftexcel/extensions/microsoftexcel-images-browser.zip
%cd /content
# Model Code
!curl -Lo /content/microsoftexcel/models/Stable-diffusion/anythingv5.safetensors https://huggingface.co/nolanaatama/nythngv5/resolve/main/nythngv5.safetensors
# ControlNet
# Remove '#' from the beginning of the line(s) below to download the selected ControlNet model(s)
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11e_sd15_ip2p.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11e_sd15_ip2p_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11e_sd15_shuffle.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11e_sd15_shuffle_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15_canny.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_canny_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11f1p_sd15_depth.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_depth_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15_inpaint.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_inpaint_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15_lineart.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_lineart_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15_mlsd.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_mlsd_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15_normalbae.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_normalbae_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15_openpose.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_openpose_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15_scribble.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_scribble_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15_seg.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_seg_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15_softedge.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15_softedge_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11p_sd15s2_lineart_anime.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11p_sd15s2_lineart_anime_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/control_v11f1e_sd15_tile.safetensors https://huggingface.co/nolanaatama/models/resolve/main/control_v11f1e_sd15_tile_fp16.safetensors
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/t2iadapter_canny_sd14v1.pth https://huggingface.co/nolanaatama/models/resolve/main/t2iadapter_canny_sd14v1.pth
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/t2iadapter_color_sd14v1.pth https://huggingface.co/nolanaatama/models/resolve/main/t2iadapter_color_sd14v1.pth
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/t2iadapter_depth_sd14v1.pth https://huggingface.co/nolanaatama/models/resolve/main/t2iadapter_depth_sd14v1.pth
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/t2iadapter_keypose_sd14v1.pth https://huggingface.co/nolanaatama/models/resolve/main/t2iadapter_keypose_sd14v1.pth
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/t2iadapter_openpose_sd14v1.pth https://huggingface.co/nolanaatama/models/resolve/main/t2iadapter_openpose_sd14v1.pth
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/t2iadapter_seg_sd14v1.pth https://huggingface.co/nolanaatama/models/resolve/main/t2iadapter_seg_sd14v1.pth
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/t2iadapter_sketch_sd14v1.pth https://huggingface.co/nolanaatama/models/resolve/main/t2iadapter_sketch_sd14v1.pth
#!curl -Lo /content/microsoftexcel/extensions/microsoftexcel-controlnet/models/t2iadapter_style_sd14v1.pth https://huggingface.co/nolanaatama/models/resolve/main/t2iadapter_style_sd14v1.pth
import shutil
shutil.rmtree('/content/microsoftexcel/embeddings')
!rm microsoftexcel.zip
!rm microsoftexcel-images-browser.zip
%cd /content/microsoftexcel
!git clone https://huggingface.co/nolanaatama/embeddings
%cd /content/microsoftexcel/models
!git clone https://huggingface.co/nolanaatama/ESRGAN
%cd /content/microsoftexcel/extensions/a1111-microsoftexcel-locon
!git checkout 04b768b
%cd /content/microsoftexcel/extensions/a1111-microsoftexcel-tagcomplete
!git checkout f9f7732
%cd /content/microsoftexcel
# Web UI tunnel
!COMMANDLINE_ARGS="--share --disable-safe-unpickle --no-half-vae --xformers --enable-insecure-extension --gradio-queue" REQS_FILE="requirements.txt" python launch.py
# Use this command below to use cloudflare tunnel
#!COMMANDLINE_ARGS="--disable-safe-unpickle --no-half-vae --xformers --enable-insecure-extension --gradio-queue --cloudflared" REQS_FILE="requirements.txt" python launch.py
