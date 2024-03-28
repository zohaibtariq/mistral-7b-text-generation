# MISTRAL 7b Text Completion Model Leveraging Apple Silicon (m1,m2, m3) GPU Power

---

## Pre Requisites

##### install xcode
```sh
xcode-select --install
```

##### compile
```sh
brew install pkgconfig cmake
```

##### install pipx
```sh
brew install pipx
```

##### symlink pipx
```sh
pipx ensurepath
```

##### install poetry
```sh
pipx install poetry
```

## STEPS TO SETUP

##### clone the rep
```sh
git clone https://github.com/zohaibtariq/mistral-7b-text-generation.git
```

##### change directory
```sh
cd mistral-7b-text-generation
```

##### to manage project dependencies
```sh
poetry init
```

##### clone c++ repo
```sh
git clone https://github.com/ggerganov/llama.cpp.git
```

##### change directory
```sh
cd llama.cpp
```

##### compile
```sh
make
```

##### add torch to dependency list
```sh
poetry add torch
```

##### add torchvision to dependency list
```sh
poetry add torchvision
```

##### add huggingface-hub to dependency list
```sh
poetry add huggingface-hub
```

##### change directory to models
```sh
cd models
```

##### check model filename to download from [here](https://huggingface.co/TheBloke/Mistral-7B-v0.1-GGUF) and replace with "**mistral-7b-v0.1.Q5_K_S.gguf**" in command blow
```sh
huggingface-cli download TheBloke/Mistral-7B-v0.1-GGUF mistral-7b-v0.1.Q5_K_S.gguf --local-dir . --local-dir-use-symlinks False
```

##### if above command produces error
```sh
pip install -U huggingface-hub
```

##### once model file is downloaded
```sh
cd ..
```

##### interact with model with some custom prompt 
```sh
./main -m ./models/mistral-7b-v0.1.Q5_K_S.gguf -t 2048 -n 128 -p 'Reasons for bad economic growth for a country?'
```

##### Follow this link from step 1 to 4 ignore if you already have it
[FOLLOW MACOS INSTALLATION](https://llama-cpp-python.readthedocs.io/en/latest/install/macos/)

##### move back
```sh
cd ..
```

##### llama cpp repo [GITHUB](https://github.com/abetlen/llama-cpp-python)
```sh
poetry add 'llama-cpp-python[server]'
```

##### make sure you are in root project folder which is mistral-7b-text-generation this will change to poetry environment (IMPORTANT DO NOT SKIP)
```sh
poetry shell
```

##### interact from python script
```sh
python3 ./main.py
```