---
title: Running MATLAB files/functions in Python (Windows & Anaconda)
date: 2022-10-12 12:00:00 -500
categories: [tutorial,software]
tags: [matlab,python,windows,anaconda,install,software]
---
# Install

1. Make sure Matlab is installed on your computer
2. Open anaconda prompt as an administrator
3. Activate the environment you want to use Matlab in
```bash
conda activate insert-name-of-environment-here
```
- if you don't know what an environment is, check this out: <https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html>
4. find the matlab directory
```bash
matlab -batch matlabroot
``` 
<https://www.scivision.dev/matlab-engine-python-install/>
5. cd to that directory
- in my case I did:
```bash
cd C:\Users\Matth>
cd C:\Program Files\MATLAB\R2021a
```
6. Run the install script
```bash
cd extern/engines/python
python setup.py install
```
7. Test to see if it works by opening a Jupyter notebook or Spyder file and run
```python
import matlab.engine
```
- if no errors, you’re good to go.
