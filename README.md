# Import libraries

import numpy as np
import pandas as pd
import ast, json
import matplotlib.pyplot as plt

import pandas as pd
# Load data
df = pd.read_csv('wine.csv',header=0)

df.head()

#Filtering the dataset to only contain “Cabernet Sauvignon”, “Pinot Noir”
# and “Chardonnay” wines

# Set 'Name' column as index
# on a Dataframe
df.set_index("variety", inplace = True)
 
# Using the operator .loc[] to
# select multiple rows with some
# particular columns
result = df.loc[["Cabernet Sauvignon", "Pinot Noir", "Chardonnay"],
               ["points"]]
 
# Show the dataframe
result


#histogram plot of the “points” column.

# Plot FacetGrid plot
plt.figure()
result.hist("points", "variety", figsize = (11,11), color="#800080")

plt.show()
plt.close()
