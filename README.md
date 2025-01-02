# real-llama-cpp-python
A simple custom wrapper for llama.cpp models in Python, support seamlessly interaction with LangChain.

## Background

Normal person would think that llama-cpp-python should run on top of llama.cpp. However, it is not simple as described `pip install llama-cpp-python`. Installing llama-cpp-python is a pain in the bum. 

Unfortunately, Langchain only supports [llama-cpp-python](https://python.langchain.com/docs/integrations/llms/llamacpp/). I had an extended Xmas leave and couldn't install the latest llama-cpp-python to run the quantized models from the latest llama.cpp. Frustrated with the process, I decided to create my own version of real-llama-cpp-python to be compatible with LangChain. 

llama.cpp can be installed or built easily. The llama.cpp community is also very active that any issue with the installation can be resolved in a few days.  

## Installation
As the name said, it is a wrapper for llama.cpp, you should first install llama.cpp into your machine 

### 1 Install llama.cpp first

- **Highly recommend this method** Clone [llama.cpp](https://github.com/ggerganov/llama.cpp/tree/master) repository and build locally, see [how to build](https://github.com/ggerganov/llama.cpp/blob/master/docs/build.md)
- On MacOS or Linux, install `llama.cpp` via [brew, flox or nix](https://github.com/ggerganov/llama.cpp/blob/master/docs/install.md). Noted that, this brew install may not support GPU.
- Use a ``llama.cpp`` Docker image, see [documentation for Docker](https://github.com/ggerganov/llama.cpp/blob/master/docs/docker.md). 
- Download pre-built binaries from [releases](https://github.com/ggerganov/llama.cpp/releases).

After successfully installed llama.cpp. You want to add the directory to your `PATH` permanently by editing your shell configuration file:
```
vim ~/.bashrc 
```
or
```
source ~/.zshrc
```
Add the following line: 
```
export PATH=$PATH:/path/to/your/llama.cpp/build/bin
```

Save and run `source ~/.bashrc`  or `source ~/.zshrc`
You should be able to run `llama-cli` and `llama-server` from any directory. Verify the accessibility, run the following commands in any directory 

```
llama-cli --help
llama-server --help
```

### 2 Install llama.cpp

```bash
pip install real-llama-cpp-python
```