# KotlinSyft All-in-one Starting Manual
This is a all-in-one manual to start with KotlinSyft for MacOS

## Requirements before starting with KotlinSyft
- **Pysyft** needs to be installed
  - Need to install Homebrew: <br>
  ```
  xcode-select --install 
  /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```
  - Install **python**:
  ```
  brew install python3
  ```
  - Install **PyTorch**:
  ```
  pip install torch torchvision
  ```
  - Clone the PySyft repository from Github
  ```
  git clone https://github.com/OpenMined/PySyft.git
  ```
  - Install **PySyft**
    - ```cd PySyft```
    - ```python setup.py install``` , with ```udacity``` caused an error
    - ```python setup.py test``` --> 6 errors occurred...
<br>

- **PyGrid** needs to be installed
