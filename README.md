
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
- Using environment in a job
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

## [Clearing Pip Cache](https://linuxhandbook.com/clear-pip-cache/)

