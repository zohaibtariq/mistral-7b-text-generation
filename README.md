
```sh
xcode-select --install
```

```sh
brew install pkgconfig cmake
```

```sh
brew install pipx
```

```sh
pipx ensurepath
```

```sh
pipx install poetry
```

```sh
mkdir mistral
```

```sh
cd mistral
```

```sh
poetry init
```

```sh
git clone https://github.com/ggerganov/llama.cpp.git
```

```sh
cd llama.cpp
```

```sh
make
```

```sh
poetry add torch
```

```sh
poetry add torchvision
```

```sh
poetry add huggingface-hub
```

```sh
cd models
```
check model filename to download from [here](https://huggingface.co/TheBloke/Mistral-7B-v0.1-GGUF) and replace with "**mistral-7b-v0.1.Q5_K_S.gguf**" in command blow
```sh
huggingface-cli download TheBloke/Mistral-7B-v0.1-GGUF mistral-7b-v0.1.Q5_K_S.gguf --local-dir . --local-dir-use-symlinks False
```

if above command produces error
```sh
pip install -U huggingface-hub
```
once model file is downloaded
```sh
cd ..
```

```sh
./main -m ./models/mistral-7b-v0.1.Q5_K_S.gguf -t 2048 -n 128 -p 'Which institute is destroying Pakistan since 1958?'
```

Follow this link from step 1 to 4 ignore if you already have it
[FOLLOW MACOS INSTALLATION](https://llama-cpp-python.readthedocs.io/en/latest/install/macos/)

```sh
cd ..
```
[GITHUB](https://github.com/abetlen/llama-cpp-python)
```sh
poetry add 'llama-cpp-python[server]'
```

make sure you are in project folder
```sh
poetry shell
```

```sh
python3 ./main.py
```