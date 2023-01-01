---
title: [Draft] Install Raypier
date: 2022-1-15 12:00:00 -500
categories: [tutorial,software]
tags: [python,raypier,optics,install,software]
---

1. download/install miniconda or anaconda
2. download code as zip and extract Raypier: <https://github.com/bryancole/raypier_optics>
3. drag it to wherever you want it, in my case I put it in my `documents/python scripts/` folder
4. watch this video to understand python environments: <https://www.youtube.com/watch?v=mIB7IZFCE_k>
4. open up anaconda prompt and type in: `conda create -n test`
    - to activate your anaconda environment: `conda activate test`
    - to deactivate: `conda deactivate`
    - to list the packages in an environment: `conda list`
5. to remove a package in an environment: `conda remove nameOfPackage`
    - to export your environment so someone else can download: `conda env export > environment.yml`
    - This page is a great source of information: <https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#sharing-an-environment>
6. whenever, you're in an environment, you can download/delete packages without affecting other virtual environments. This prevents library conflicts when working on various projects
7. To find your environments folder, type: `conda env list`
8. find the environment file in the raypier folder, in my case the path was: `C:\Users\Matth\Documents\Python Scripts\raypier_optics-master\environment.yaml`
9. On your anaconda prompt type in: 
```
conda env create -f C:\Users\Matth\Documents\Python Scripts\raypier_optics-master\environment.yaml
```
10. navigate to your env folder and drop in