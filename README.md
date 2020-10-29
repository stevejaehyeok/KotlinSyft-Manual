# KotlinSyft Demo Manual
KotlinSyft: https://github.com/OpenMined/KotlinSyft

This is a step-by-step manual to start with KotlinSyft demo for MacOS.

I made it by communicating with the developers from Openmined

Created for Team Revivers (SW Maestro 11th)

## Requirements before starting with KotlinSyft
- **PyGrid** needs to be installed
  - Clone the dev branch and Change the directory to it:
  ```
  git clone --single-branch --branch dev https://github.com/OpenMined/PyGrid.git
  cd PyGrid
  ```

- Install **docker**
  - [Link to it](https://docs.docker.com/get-docker/)
- Install **docker-compose** (no need for MacOS)
  - Docker apps includes the Compose

- Execute ```docker-compose``` in the command line
  ```
  docker-compose up --build --force-recreate
  ```

- Install **PySyft** (master branch) in the virtual environment
  ```
  virtualenv -p python3 venv
  source venv/bin/activate
  pip install syft
  pip install jupyter==1.0.0
  pip install notebook==5.7.8
  git clone https://github.com/OpenMined/PySyft
  cd PySyft
  // git checkout tags/v0.2.8 -b v0.2.8 (This version tends to be unstable, thus use the latest master or check with the developers)
  // git checkout master (automatically checked out the master branch)
  pip install .
  ```

- Host Jupyter Notebook
  ```
  jupyter notebook
  ```
- In the Jupyter Notebook console, navigate to ```examples/tutorials/model-centric-fl```
- Run the notebook ```Create Plan```. This should host the model the model on PyGrid.
  - Set variable ```gridAddress``` to local-ip-address:port-that-PyGrid-node-is-running
  ```
  ex) gridAddress = <local-ip>:5000
  ```
- Run demo-app in the KotlinSyft project
- Enter the ip address with port (ex. xxx.xxx.x.x:5000)
- Press button ```START FOREGROUND```

- conv_backward codes (from: https://becominghuman.ai/back-propagation-in-convolutional-neural-networks-intuition-and-code-714ef1c38199)
```
def conv_backward(dH, cache):
    '''
    The backward computation for a convolution function
    
    Arguments:
    dH -- gradient of the cost with respect to output of the conv layer (H), numpy array of shape (n_H, n_W) assuming channels = 1
    cache -- cache of values needed for the conv_backward(), output of conv_forward()
    
    Returns:
    dX -- gradient of the cost with respect to input of the conv layer (X), numpy array of shape (n_H_prev, n_W_prev) assuming channels = 1
    dW -- gradient of the cost with respect to the weights of the conv layer (W), numpy array of shape (f,f) assuming single filter
    '''
    
    # Retrieving information from the "cache"
    (X, W) = cache
    
    # Retrieving dimensions from X's shape
    (n_H_prev, n_W_prev) = X.shape
    
    # Retrieving dimensions from W's shape
    (f, f) = W.shape
    
    # Retrieving dimensions from dH's shape
    (n_H, n_W) = dH.shape
    
    # Initializing dX, dW with the correct shapes
    dX = np.zeros(X.shape)
    dW = np.zeros(W.shape)
    
    # Looping over vertical(h) and horizontal(w) axis of the output
    for h in range(n_H):
        for w in range(n_W):
            dX[h:h+f, w:w+f] += W * dH(h,w)
            dW += X[h:h+f, w:w+f] * dH(h,w)
    
    return dX, dW
```
