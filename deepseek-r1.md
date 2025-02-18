# DeepSeek R1 Distill Deployment on Ubuntu 24.04 LTS

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|

DeepSeek R1 is released on Jan 20, 2025 and it is Open Source LLM (Large Language Model) developed by DeepSeek Company in China.

## 01 Install Docker

```
sudo apt update

sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update

sudo apt install docker-ce
```

## 02 Install NVIDIA Container Toolkit (Optional)

If you have NVIDIA Display Card and the proprietary driver has been installed.  You need to install [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html#installation) in order to allow NVIDIA driver to communicate with Docker Container.

## 03 Install Ollama

### CPU only

```
sudo docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama --restart always ollama/ollama
```

### NVIDIA Display Card only

```
sudo docker run -d --gpus=all -v ollama:/root/.ollama -p 11434:11434 --name ollama --restart always ollama/ollama
```

### AMD Display Card only

```
sudo docker run -d --device /dev/kfd --device /dev/dri -v ollama:/root/.ollama -p 11434:11434 --name ollama --restart always ollama/ollama:rocm
```

## 04 Import DeepSeek R1 Distill Models

The followings are 4bit models.

### Multi-core CPU and 8GB RAM

```
sudo docker exec -it ollama ollama run hf.co/bartowski/DeepSeek-R1-Distill-Qwen-1.5B-GGUF:Q4_0
```

### Multi-core CPU and 16GB RAM

```
sudo docker exec -it ollama ollama run hf.co/bartowski/DeepSeek-R1-Distill-Qwen-7B-GGUF:Q4_0
```

### Multi-core CPU and 32GB RAM

```
sudo docker exec -it ollama ollama run hf.co/bartowski/DeepSeek-R1-Distill-Qwen-14B-GGUF:Q4_0
```

### Multi-core CPU and 64GB RAM

```
sudo docker exec -it ollama ollama run hf.co/bartowski/DeepSeek-R1-Distill-Qwen-32B-GGUF:Q4_0
```

When the model is imported, you can try to interactive with the model.  To quit is to enter ```/bye```.

## 05 Install Open WebUI

### Without Login

```
sudo docker run -d -p 3000:8080 -v ollama:/root/.ollama -v open-webui:/app/backend/data -e WEBUI_AUTH=False --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```

### With Login

```
sudo docker run -d -p 3000:8080 -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```

Once ```With Login``` is implemented, you are very hard to disable it unless you re-install Docker, Ollama and Open WebUI.

Once Open WebUI installed, you can access the frontend by going to :

```
http://localhost:3000
```

## 06 Install AnythingLLM (Optional)

```
sudo docker pull mintplexlabs/anythingllm

export STORAGE_LOCATION=$HOME/anythingllm && \
mkdir -p $STORAGE_LOCATION && \
touch "$STORAGE_LOCATION/.env" && \

sudo docker run -d -p 3001:3001 \
--cap-add SYS_ADMIN \
-v ${STORAGE_LOCATION}:/app/server/storage \
-v ${STORAGE_LOCATION}/.env:/app/server/.env \
-e STORAGE_DIR="/app/server/storage" \
--restart always \
mintplexlabs/anythingllm
```

To run the frontend :

```
http://localhost:3001
```

## 07 Mobile Phone (Optional)

Install PocketPal AI from the Google Play Store or Apple Store and import models to the phone.  Make sure use 1.5b or 7b/8b depends on the amount of RAM on your phone.

## Reference

- [DeepSeek Official Site](https://www.deepseek.com/)  
- [DeepSeek GitHub](https://github.com/deepseek-ai/DeepSeek-R1)  
- [Ollama Official Site](https://ollama.com/)
- [Open WebUI Official Site](https://openwebui.com/)  
- [Open WebUI GitHub](https://github.com/open-webui/open-webui)  
- [Huggingface - bartowski](https://huggingface.co/bartowski)  
- [Anything LLM Desktop](https://anythingllm.com/desktop)  
- [PocketPal AI Google Play Store](https://play.google.com/store/apps/details?id=com.pocketpalai)  
- [PocketPal AI GitHub](https://github.com/a-ghorbani/pocketpal-ai)  

|[Home](/README.md)|[Projects](/projects.md)|[Articles](/articles.md)|[Apophthegm](/apophthegm.md)|[About](/about.md)|
