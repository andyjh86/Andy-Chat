# Andy-Chat
A chatbot with a simple gui using a local Llama style model, llama-cpp-python & LangChain

You'll need a few things - 

Download Visual Studio and install making sure C++ support is selected.
Download CMAKE and add it to path (in windows 11 you can search "edit the system Environment Variables" and click Environment Variables)
pip install the python package LangChain (Best practice with -m flag. I use python -m pip install LangChain)

Installing llama-cpp-python can be a little tricky if you're using CMD and a windows machine. You need to activate each flag in the CMD environment at the same time when using pip.
The following is an example of how I installed it with the proper flags to force cuBLAS

SET LLAMA_CLBLAST=1 && SET CMAKE_ARGS="-DLLAMA_CLBLAST=on" && SET FORCE_CMAKE=1 && python -m pip install llama-cpp-python

note how the flags are joined with &&. pip is then installed the same way via the same line.

If you've previously installed llama-cpp-python and it only has cpu support then you will need to force reinstall.

The following is an example of the re-install

SET LLAMA_CLBLAST=1 && SET FORCE_CMAKE=1 && SET CMAKE_ARGS=-DLLAMA_CUBLAS=on && python -m pip install llama-cpp-python --force-reinstall --upgrade --no-cache-dir

You will also need the Tk package to support the GUI using Tkinter 
