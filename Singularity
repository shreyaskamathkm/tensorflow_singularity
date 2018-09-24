Bootstrap: docker
From: shreyaskamathkm/deeplearning


%environment
  # use bash as default shell
  SHELL=/bin/bash
  export SHELL
  PATH="/opt/conda/bin:$PATH"
  export PATH


%setup
  # runs on host - the path to the image is $SINGULARITY_ROOTFS

%post
  # post-setup script

  # load environment variables
  . /environment

  # make environment file executable
  mkdir /data
  chmod +x /environment

  # default mount paths, files
  touch /usr/bin/nvidia-smi
  
  # user requests 
  /opt/conda/bin/conda install python=3.6
  /opt/conda/bin/conda install -c conda-forge onnx spectrum nibabel
  /opt/conda/bin/conda update -y --all	
  /opt/conda/bin/conda clean -ya
  pip install natsort
  pip install --upgrade tensorflow-gpu
  pip install keras

%runscript
  # executes with the singularity run command
  # delete this section to use existing docker ENTRYPOINT command

%test
  # test that script is a success
