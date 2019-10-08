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
## STEP 3:
for this step we read the json and we print it to see the keys and other things that we will need for the next things.
````
breast_cancer = datasets.load_breast_cancer()
breast_cancer
````
If you want to see the picture for this step, you can see the output:
https://github.com/Adrianc1234/Cancer-/blob/master/imagen_1.png

## STEP 4:
In this step we make a DataFrame and we call the json and use the key data to make the table with feature_names that has all the titles for the columns on the table after that, we make a column with the name Types and we call from the json the values that are in the key target and put them inside it, and after that we say how the Data Frame will read the title and we delete the space on them and for the end we apply the function to change 0 or 1 by the names on target_names.
````
data= pd.DataFrame(breast_cancer.data, columns= breast_cancer.feature_names)
data['Types']= breast_cancer.target
data.columns = data.columns.str.replace(" ","")
data.Types= data.Types.apply(cancer)
data.head()
````
you can see the output of this step here:

And to see the some statistical calculations we make this code:
````
data.describe()
````
we can see the target_names using:
````
breast_cancer.target_names
````
if we want to see the all the information about the Data Frame we can run this code:
````
data.info()
````
we can check if some column has a empty values with this function, where .isnull() checks the empty values and the end .sum() make a sum to count how many b¿values are empty:
````
data.isnull().sum()
````
if we check how many types of values are in Types column, we use this function where the .Type say the column that we will check and the other function that is .value_counts() make the count of the values and print it.
````
data.Types.value_counts()
````
## STEP 5:
### we classify the different values in one specific Data Frame.

