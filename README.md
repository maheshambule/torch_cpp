## How to compile pybind11 module

1. Run commands below
```
pip install torch
pip install torchserve
git clone --recursive https://github.com/maheshambule/torch_cpp.git

```

2. Modify the CMakeLists.txt to add set CMAKE_PREFIX_PATH path to Torch package.
Run command below to find out the Torch package path.

```
python -c 'import torch;import os;print(os.path.dirname(torch.__file__))'
vi CMakeLists.txt
```

3. Then compile the pybind [module](bindings/src/pt_c_inference.cpp) using pip and install the package.

```
cd bindings
pip install .
```

4. Run the inference handlers with Torch C++ with pybind11 and Torch Python API.

```
cd ..
python handler.py #torch C++ with pybind11
python handler_py.py  #torch python
```

