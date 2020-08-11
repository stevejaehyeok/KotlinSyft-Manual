# KotlinSyft All-in-one Starting Manual
This is a all-in-one manual to start with KotlinSyft for MacOS

## Requirements before starting with KotlinSyft
- **PyGrid** needs to be installed
  - Clone the dev branch and Change the directory to it:
  ```
  git clone --single-branch --branch dev https://github.com/OpenMined/PyGrid.git
  cd PyGrid
  ```
<br>

- Install **docker**
  - [Link to it](https://docs.docker.com/get-docker/)
- Install **docker-compose**
  - Docker apps includes the Compose
  
<br>

- Execute ```docker-compose``` in the command line
  ```
  docker-compose up --build --force-recreate
  ```

<br>

- Install **PySyft** (newest version: v0.2.8) in the virtual environment
  ```
  virtualenv -p python3 venv
  source venv/bin/activate
  pip install syft
  pip install jupyter==1.0.0
  pip install notebook==5.7.8
  git clone https://github.com/OpenMined/PySyft
  cd PySyft
  git checkout tags/v0.2.8 -b v0.2.8
  ```

- Host Jupyter Notebook
  ```
  jupyter notebook
  ```
- In the Jupyter Notebook console, navigate to ```examples/tutorials/model-centric-fl```
- Run the notebook ```Create Plan```. This should host the model the model on PyGrid.

