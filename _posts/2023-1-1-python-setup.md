---
title: Getting started with Python (Draft) 
date: 2023-1-1 12:00:00 -500
categories: [tutorial,software]
tags: [python,windows,install,software]
---

# What is Conda Environment?

Essentially it is a collection of libraries/code that can run independently. I.E. you can create multiple environments with multiple different languages installed (yes, can be something other than Python), and each environment has its own libraries/packages that operate independently from other environments.

# Creating a new environment and Installing Sypder

Link: <https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html>

1. Type: conda create -n spyder python=3.6

* where spyder is the name of the environment and python=3.6 is installing version 3.6 of python into the environment.

2. Type: conda activate spyder

3. conda install spyder

what also works is: conda install spyder=4

spyder