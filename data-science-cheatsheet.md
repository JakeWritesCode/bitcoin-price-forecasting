# Jake's Data Science Cheatsheet
This is my data sciencey cheat sheet where i'll keep examples of all the numpy / pandas / sklearn / keras'y 
stuff so I don't have to copy and paste from old projects or Google every time I do data science work.


## Pandas

### Give me information!
Here are some quick commands to get info out of a dataframe.

```python
import pandas as pd
df = pd.DataFrame()

# Get the shape of the df as a tuple.
df.shape

# Get the column names
df.columns

# Get the dtypes of each column
df.dtypes

```


### Sampling
To sample a dataframe at a flat sample rate:

```python
import pandas as pd

df = pd.DataFrame()
# First, use rolling to modify the dataset according to your sampling strategy.
# Here, we're doing a 1:60 rolling mean.
# You need to specify the cols to work on or it'll drop nuisance cols such as tiemstamps.
df[["cols", "to", "average"]] = df[["cols", "to", "average"]].rolling(60).mean()

# Then, just do the sampling.
# Obvs make the two sample rates match.
df = df.iloc[::60, :]
```

### Type Conversion
Convert string column to datetime:
```python
df["column_name"] = pd.to_datetime(df['column_name'], format="specify your format")
```

### Changing column names
To change the name of columns:
```python
df.rename(columns={"old_name_1": "new_name_1"})
```

### Filtering
This is a pretty big topic, so I'm just going to throw good examples in as I find them.

```python
import pandas as pd
from datetime import datetime
df = pd.DataFrame()

# Filter by column name is greate than value, datetime in this case.
df = df.loc[df["column_name"] > datetime(2021, 7, 1)]

```



## Matplotlib

### Generally useful snippets...
```python
import matplotlib.pyplot as plt

# Set the size of all future graph outputs globally.
plt.rcParams["figure.figsize"] = (20,3)


```

## Line graph with 