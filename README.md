# Submission-for-DCIC-Challenge

The FGMRES.json file contains information about the solver to be used. It needs to be stored anywhere in the dcic folder. Then, in the script in line 210 it needs to be specified where this file is located. The python script itself goes under src/algorithms as usual in this benchmark.

The code runs with algebraic multigrid solvers for computational efficiency. This requires both the AMGX library and the Python Interface pyamgx. If you struggle with the installation, please contact me via klees@uni-wuppertal.de

### Install NVIDIA AMGX

You need to build and install [NVIDIA AMGX](https://github.com/NVIDIA/AMGX). Follow the official instructions.


### Install PyAMGX

Install `pyamgx` (must be done after AMGX is built):

Follow the official [PyAMGX](https://pyamgx.readthedocs.io/en/latest/install.html) instruction.


### Troubleshooting
#### Installation Problems
- if problems like `ModuleNotFoundError: No module named 'numpy' ` appear durring the PyAmgx installation try to downgrade numpy to numpy==1.26.4 (last version before 2.0.0) and if not done already update pip, setuptools and wheel

- Also before installing `PyAMGX` dont forget to set the correct environment variable for `AMGX_DIR` and `AMGX_BUILD_DIR`

####  Execution Problems
- if problems like `pyamgx.AMGXError: Error initializing amgx core` occur when running this project, check if all environment variables for CUDA and AMGX are correct:
```bash
echo $AMGX_DIR
echo $AMGX_BUILD_DIR
echo $LD_LIBRARY_PATH
echo $CPATH
echo $PATH
```
and check if the `FGMRES.json` file under the `configs` folder is found correctly.


---
