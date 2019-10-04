# DATA BASE ABOUT CANCER USING EDA-CANCER
# STEPS:
## STEP 1:
we imported the libreries that we used to make that the functions or tools works
these are the libreries that you need to import and you need to have installed on your computer like mathplotlib that is a librery that python does not have installed.
````
from sklearn import datasets
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
````
## STEP 2:
we made a function to get the target names of the file that we will read and after that we return the value of the names inside of the target names, in this case the names are "malignant" and "benign".
````
def cancer(value):
    cancer = breast_cancer.target_names[value]
    return cancer
#python lamda function
cancer_function = lambda x: breast_cancer.target_names[x]
````
## step 3:
for this step we read the json and we print it to see the keys and other things that we will need for the next things.
````
breast_cancer = datasets.load_breast_cancer()
breast_cancer
````
