
## [Conda Environment](https://dashboard.hpc.unimelb.edu.au/software/anaconda/)

- Set conda environment path 

  To change the conda environments location to a project directory (e.g. /data/gpfs/projects/punim0001), add this to your ~/.bash_profile file
  ```
  export CONDA_ENVS_PATH=/data/gpfs/projects/punim0001/anaconda3/envs
  ```
- Create a conda environment
  
  Create a conda env called ENV_NAME
  ```
  module load Anaconda3/2022.10
  conda create -n ENV_NAME python=3.x -y
  ```
- Activate conda environment
  ```
  eval "$(conda shell.bash hook)"
  conda activate ENV_NAME
  ```
  or
  ```
  source activate ENV_NAME
  ```
- Using the environment in a job
  ```
  module load Anaconda3/2022.10
  eval "$(conda shell.bash hook)"
  conda activate ENV_NAME
  ```
- Remove a conda environment
  ```
  conda env list
  conda deactivate
  conda remove --name ENV_NAME --all
  ```
## [Install PyTorch](https://pytorch.org/)
- Install package
  After activating conda environment
  ```
  conda install ...
  ```
  or
  ```
  pip install ...
  ```
- Check if PyTorch is installed correctly and is working as expected
  1. Import PyTorch and Check Version
  ```
  python -c "import torch; print(torch.__version__)"
  ```
  2. Perform a Simple Tensor Operation
  ```
  python -c "import torch; x = torch.rand(5, 3); print(x)"
  ```
  3. Check CUDA Availability
  ```
  python -c "import torch; print(torch.cuda.is_available())"
  ```
  4. Create a Tensor on GPU (If CUDA is Available):
  ```
  python -c "import torch; x = torch.rand(5, 3); print(x.to('cuda') if torch.cuda.is_available() else 'CUDA not available')"
  ```

## [Clearing Pip Cache](https://linuxhandbook.com/clear-pip-cache/)

- Have a look at the cache
  ```
  # check the cache size of pip
  pip cache info
  # check the cache of the individual packages
  pip cache list
  # check the directory where the cache resides
  pip cache dir
  ```
- Remove Pip cache
  ```
  # remove a specific package
  pip cache remove [package_name]
  # remove everything from the pip cache
  pip cache purge 
  ```
## interactive gpu
- Kill any running python process
  ```
  pkill -9 python
  ```
