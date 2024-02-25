# Pandas

## Pandas basics
Pandas is a Python library used for working with data sets. It has functions for analyzing, cleaning, exploring, and manipulating data. The name "Pandas" has a reference to both "Panel Data", and "Python Data Analysis" and was created by Wes McKinney in 2008.

Pandas allows us to analyze big data and make conclusions based on statistical theories. Pandas can clean messy data sets, and make them readable and relevant. Relevant data is very important in data science.

Create an alias with the `as` keyword while importing:


```python
# import pandas
import pandas as pd
# import numpy
import numpy as np
```

Now the Pandas package can be referred to as `pd` instead of `pandas`.

## Series


```python
name = ['Andy', 'Ron', 'James', 'Edy']
myseries1 = pd.Series(name)
```


```python
print(myseries1)
```

    0     Andy
    1      Ron
    2    James
    3      Edy
    dtype: object



```python
age = [21, 35, 54, 33]
myseries2 = pd.Series(age)
```


```python
print(myseries2)
```

    0    21
    1    35
    2    54
    3    33
    dtype: int64


## DataFrame
A Pandas DataFrame is a 2 dimensional data structure, like a 2 dimensional array, or a table with rows and columns.

Create simple DataFrame


```python
import pandas as pd

data = {
  "calories": [420, 380, 390],
  "duration": [50, 40, 45]
}

#load data into a DataFrame object:
df = pd.DataFrame(data)

print(df) 
```

       calories  duration
    0       420        50
    1       380        40
    2       390        45


**Locate Row**: As you can see from the result above, the DataFrame is like a table with rows and columns.
Pandas use the `loc` attribute to return one or more specified row(s)


```python
#refer to the row index:
print(df.loc[0])
```

    calories    420
    duration     50
    Name: 0, dtype: int64



```python
#use a list of indexes:
print(df.loc[[0, 1]])
```

       calories  duration
    0       420        50
    1       380        40


**Named Indexes**: With the index argument, you can name your own indexes.


```python
import pandas as pd

data = {
  "calories": [420, 380, 390],
  "duration": [50, 40, 45]
}

df = pd.DataFrame(data, index = ["day1", "day2", "day3"])

print(df) 
```

          calories  duration
    day1       420        50
    day2       380        40
    day3       390        45


**Locate Named Indexes**: 
Use the named index in the loc attribute to return the specified row(s).


```python
#refer to the named index:
print(df.loc["day2"])
```

    calories    380
    duration     40
    Name: day2, dtype: int64


**Read CSV Files**: 
A simple way to store big data sets is to use CSV files (comma separated files).
CSV files contains plain text and is a well know format that can be read by everyone including Pandas.


```python
import pandas as pd

df = pd.read_csv('data/gdp.csv')
```


```python
df.head()  # first five rows
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country Name</th>
      <th>Country Code</th>
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aruba</td>
      <td>ABW</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>2.727850e+09</td>
      <td>2.790850e+09</td>
      <td>2.962907e+09</td>
      <td>2.983635e+09</td>
      <td>3.092429e+09</td>
      <td>3.276184e+09</td>
      <td>3.395799e+09</td>
      <td>2.558906e+09</td>
      <td>3.103184e+09</td>
      <td>3.544708e+09</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Africa Eastern and Southern</td>
      <td>AFE</td>
      <td>1.847810e+10</td>
      <td>1.936631e+10</td>
      <td>2.050647e+10</td>
      <td>2.224273e+10</td>
      <td>2.429433e+10</td>
      <td>2.661956e+10</td>
      <td>2.873279e+10</td>
      <td>3.159296e+10</td>
      <td>...</td>
      <td>9.863430e+11</td>
      <td>1.006990e+12</td>
      <td>9.325130e+11</td>
      <td>8.900510e+11</td>
      <td>1.028390e+12</td>
      <td>1.012520e+12</td>
      <td>1.006190e+12</td>
      <td>9.288800e+11</td>
      <td>1.086530e+12</td>
      <td>1.185140e+12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>5.377778e+08</td>
      <td>5.488889e+08</td>
      <td>5.466667e+08</td>
      <td>7.511112e+08</td>
      <td>8.000000e+08</td>
      <td>1.006667e+09</td>
      <td>1.400000e+09</td>
      <td>1.673333e+09</td>
      <td>...</td>
      <td>2.014642e+10</td>
      <td>2.049713e+10</td>
      <td>1.913422e+10</td>
      <td>1.811657e+10</td>
      <td>1.875346e+10</td>
      <td>1.805322e+10</td>
      <td>1.879944e+10</td>
      <td>1.995593e+10</td>
      <td>1.426650e+10</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Africa Western and Central</td>
      <td>AFW</td>
      <td>1.041165e+10</td>
      <td>1.113592e+10</td>
      <td>1.195171e+10</td>
      <td>1.268581e+10</td>
      <td>1.384900e+10</td>
      <td>1.487476e+10</td>
      <td>1.584558e+10</td>
      <td>1.442849e+10</td>
      <td>...</td>
      <td>8.340970e+11</td>
      <td>8.945050e+11</td>
      <td>7.692630e+11</td>
      <td>6.921150e+11</td>
      <td>6.856300e+11</td>
      <td>7.681580e+11</td>
      <td>8.234060e+11</td>
      <td>7.869620e+11</td>
      <td>8.449280e+11</td>
      <td>8.753940e+11</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Angola</td>
      <td>AGO</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>1.323390e+11</td>
      <td>1.359670e+11</td>
      <td>9.049642e+10</td>
      <td>5.276162e+10</td>
      <td>7.369016e+10</td>
      <td>7.945069e+10</td>
      <td>7.089796e+10</td>
      <td>4.850156e+10</td>
      <td>6.650513e+10</td>
      <td>1.067830e+11</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 65 columns</p>
</div>




```python
df.tail() # last five rows
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country Name</th>
      <th>Country Code</th>
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>261</th>
      <td>Kosovo</td>
      <td>XKX</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>6.735329e+09</td>
      <td>7.074395e+09</td>
      <td>6.295848e+09</td>
      <td>6.682677e+09</td>
      <td>7.180765e+09</td>
      <td>7.878760e+09</td>
      <td>7.899738e+09</td>
      <td>7.717145e+09</td>
      <td>9.412034e+09</td>
      <td>9.409474e+09</td>
    </tr>
    <tr>
      <th>262</th>
      <td>Yemen, Rep.</td>
      <td>YEM</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>4.041523e+10</td>
      <td>4.322859e+10</td>
      <td>4.244449e+10</td>
      <td>3.131782e+10</td>
      <td>2.684223e+10</td>
      <td>2.160616e+10</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>263</th>
      <td>South Africa</td>
      <td>ZAF</td>
      <td>8.748597e+09</td>
      <td>9.225996e+09</td>
      <td>9.813996e+09</td>
      <td>1.085420e+10</td>
      <td>1.195600e+10</td>
      <td>1.306899e+10</td>
      <td>1.421139e+10</td>
      <td>1.582139e+10</td>
      <td>...</td>
      <td>4.008860e+11</td>
      <td>3.811990e+11</td>
      <td>3.467100e+11</td>
      <td>3.235860e+11</td>
      <td>3.814490e+11</td>
      <td>4.052610e+11</td>
      <td>3.893300e+11</td>
      <td>3.382910e+11</td>
      <td>4.201180e+11</td>
      <td>4.052710e+11</td>
    </tr>
    <tr>
      <th>264</th>
      <td>Zambia</td>
      <td>ZMB</td>
      <td>7.130000e+08</td>
      <td>6.962857e+08</td>
      <td>6.931429e+08</td>
      <td>7.187143e+08</td>
      <td>8.394286e+08</td>
      <td>1.082857e+09</td>
      <td>1.264286e+09</td>
      <td>1.368000e+09</td>
      <td>...</td>
      <td>2.803724e+10</td>
      <td>2.714102e+10</td>
      <td>2.125122e+10</td>
      <td>2.095841e+10</td>
      <td>2.587360e+10</td>
      <td>2.631151e+10</td>
      <td>2.330867e+10</td>
      <td>1.811064e+10</td>
      <td>2.209642e+10</td>
      <td>2.916378e+10</td>
    </tr>
    <tr>
      <th>265</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>1.052990e+09</td>
      <td>1.096647e+09</td>
      <td>1.117602e+09</td>
      <td>1.159512e+09</td>
      <td>1.217138e+09</td>
      <td>1.311436e+09</td>
      <td>1.281750e+09</td>
      <td>1.397002e+09</td>
      <td>...</td>
      <td>1.909102e+10</td>
      <td>1.949552e+10</td>
      <td>1.996312e+10</td>
      <td>2.054868e+10</td>
      <td>1.758489e+10</td>
      <td>3.415607e+10</td>
      <td>2.183223e+10</td>
      <td>2.150970e+10</td>
      <td>2.837124e+10</td>
      <td>2.736663e+10</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 65 columns</p>
</div>




```python
df.sample(6) # random n=6 number of rows
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country Name</th>
      <th>Country Code</th>
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>233</th>
      <td>Thailand</td>
      <td>THA</td>
      <td>2.760751e+09</td>
      <td>3.034038e+09</td>
      <td>3.308913e+09</td>
      <td>3.540403e+09</td>
      <td>3.889130e+09</td>
      <td>4.388938e+09</td>
      <td>5.279231e+09</td>
      <td>5.638461e+09</td>
      <td>...</td>
      <td>4.203340e+11</td>
      <td>4.073390e+11</td>
      <td>4.012960e+11</td>
      <td>4.133660e+11</td>
      <td>4.563570e+11</td>
      <td>5.067540e+11</td>
      <td>5.439770e+11</td>
      <td>5.004570e+11</td>
      <td>5.055680e+11</td>
      <td>4.954230e+11</td>
    </tr>
    <tr>
      <th>211</th>
      <td>El Salvador</td>
      <td>SLV</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>8.777200e+08</td>
      <td>9.295200e+08</td>
      <td>9.762000e+08</td>
      <td>...</td>
      <td>2.199096e+10</td>
      <td>2.259347e+10</td>
      <td>2.343824e+10</td>
      <td>2.419143e+10</td>
      <td>2.497919e+10</td>
      <td>2.602085e+10</td>
      <td>2.688114e+10</td>
      <td>2.493008e+10</td>
      <td>2.945124e+10</td>
      <td>3.248872e+10</td>
    </tr>
    <tr>
      <th>251</th>
      <td>United States</td>
      <td>USA</td>
      <td>5.433000e+11</td>
      <td>5.633000e+11</td>
      <td>6.051000e+11</td>
      <td>6.386000e+11</td>
      <td>6.858000e+11</td>
      <td>7.437000e+11</td>
      <td>8.150000e+11</td>
      <td>8.617000e+11</td>
      <td>...</td>
      <td>1.684320e+13</td>
      <td>1.755070e+13</td>
      <td>1.820600e+13</td>
      <td>1.869510e+13</td>
      <td>1.947730e+13</td>
      <td>2.053310e+13</td>
      <td>2.138100e+13</td>
      <td>2.106050e+13</td>
      <td>2.331510e+13</td>
      <td>2.543970e+13</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Azerbaijan</td>
      <td>AZE</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>7.416056e+10</td>
      <td>7.523979e+10</td>
      <td>5.307624e+10</td>
      <td>3.786700e+10</td>
      <td>4.086663e+10</td>
      <td>4.711247e+10</td>
      <td>4.817424e+10</td>
      <td>4.269300e+10</td>
      <td>5.482541e+10</td>
      <td>7.872106e+10</td>
    </tr>
    <tr>
      <th>134</th>
      <td>Latin America &amp; Caribbean</td>
      <td>LCN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>6.360880e+12</td>
      <td>6.482210e+12</td>
      <td>5.420470e+12</td>
      <td>5.285690e+12</td>
      <td>5.866300e+12</td>
      <td>5.742580e+12</td>
      <td>5.660900e+12</td>
      <td>4.809520e+12</td>
      <td>5.553340e+12</td>
      <td>6.302490e+12</td>
    </tr>
    <tr>
      <th>244</th>
      <td>Turkiye</td>
      <td>TUR</td>
      <td>7.566667e+09</td>
      <td>7.988889e+09</td>
      <td>8.922222e+09</td>
      <td>1.035556e+10</td>
      <td>1.117778e+10</td>
      <td>1.196667e+10</td>
      <td>1.410000e+10</td>
      <td>1.564444e+10</td>
      <td>...</td>
      <td>9.577990e+11</td>
      <td>9.389350e+11</td>
      <td>8.643140e+11</td>
      <td>8.696830e+11</td>
      <td>8.589880e+11</td>
      <td>7.789720e+11</td>
      <td>7.610060e+11</td>
      <td>7.203380e+11</td>
      <td>8.198650e+11</td>
      <td>9.071180e+11</td>
    </tr>
  </tbody>
</table>
<p>6 rows × 65 columns</p>
</div>




```python
df.shape # sample data's rows and columns (dimensions)
```




    (266, 65)



## Statistics
 


```python
df.describe() # basic statistics of each column
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>1968</th>
      <th>1969</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1.260000e+02</td>
      <td>1.270000e+02</td>
      <td>1.280000e+02</td>
      <td>1.280000e+02</td>
      <td>1.280000e+02</td>
      <td>1.400000e+02</td>
      <td>1.430000e+02</td>
      <td>1.460000e+02</td>
      <td>1.510000e+02</td>
      <td>1.510000e+02</td>
      <td>...</td>
      <td>2.590000e+02</td>
      <td>2.600000e+02</td>
      <td>2.580000e+02</td>
      <td>2.580000e+02</td>
      <td>2.580000e+02</td>
      <td>2.580000e+02</td>
      <td>2.580000e+02</td>
      <td>2.570000e+02</td>
      <td>2.550000e+02</td>
      <td>2.420000e+02</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>7.295340e+10</td>
      <td>7.486095e+10</td>
      <td>7.866325e+10</td>
      <td>8.518003e+10</td>
      <td>9.404310e+10</td>
      <td>9.429472e+10</td>
      <td>1.044707e+11</td>
      <td>1.087439e+11</td>
      <td>1.136922e+11</td>
      <td>1.255384e+11</td>
      <td>...</td>
      <td>2.482324e+12</td>
      <td>2.543694e+12</td>
      <td>2.404723e+12</td>
      <td>2.437760e+12</td>
      <td>2.613242e+12</td>
      <td>2.776038e+12</td>
      <td>2.817910e+12</td>
      <td>2.741965e+12</td>
      <td>3.169612e+12</td>
      <td>3.477949e+12</td>
    </tr>
    <tr>
      <th>std</th>
      <td>2.186745e+11</td>
      <td>2.282798e+11</td>
      <td>2.438626e+11</td>
      <td>2.628174e+11</td>
      <td>2.877302e+11</td>
      <td>3.004630e+11</td>
      <td>3.282238e+11</td>
      <td>3.474791e+11</td>
      <td>3.696229e+11</td>
      <td>4.066426e+11</td>
      <td>...</td>
      <td>8.401587e+12</td>
      <td>8.612905e+12</td>
      <td>8.172392e+12</td>
      <td>8.309606e+12</td>
      <td>8.845330e+12</td>
      <td>9.414854e+12</td>
      <td>9.553275e+12</td>
      <td>9.325109e+12</td>
      <td>1.067562e+13</td>
      <td>1.131793e+13</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.201202e+07</td>
      <td>1.159202e+07</td>
      <td>9.122751e+06</td>
      <td>1.084010e+07</td>
      <td>1.271247e+07</td>
      <td>1.359393e+07</td>
      <td>1.446908e+07</td>
      <td>1.583511e+07</td>
      <td>1.460000e+07</td>
      <td>1.585000e+07</td>
      <td>...</td>
      <td>3.861589e+07</td>
      <td>3.876098e+07</td>
      <td>3.681194e+07</td>
      <td>4.162906e+07</td>
      <td>4.527660e+07</td>
      <td>4.801526e+07</td>
      <td>5.412320e+07</td>
      <td>5.174659e+07</td>
      <td>6.019641e+07</td>
      <td>5.906598e+07</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>5.151683e+08</td>
      <td>5.111424e+08</td>
      <td>5.185977e+08</td>
      <td>5.150864e+08</td>
      <td>5.415796e+08</td>
      <td>5.199337e+08</td>
      <td>5.894217e+08</td>
      <td>5.190310e+08</td>
      <td>5.605380e+08</td>
      <td>5.988611e+08</td>
      <td>...</td>
      <td>8.486163e+09</td>
      <td>9.034786e+09</td>
      <td>8.752203e+09</td>
      <td>8.620984e+09</td>
      <td>9.319389e+09</td>
      <td>1.002804e+10</td>
      <td>1.035516e+10</td>
      <td>9.754600e+09</td>
      <td>1.056293e+10</td>
      <td>1.379943e+10</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2.661058e+09</td>
      <td>2.417629e+09</td>
      <td>2.319980e+09</td>
      <td>2.680117e+09</td>
      <td>2.853831e+09</td>
      <td>2.913602e+09</td>
      <td>3.039859e+09</td>
      <td>3.145743e+09</td>
      <td>3.330372e+09</td>
      <td>3.787077e+09</td>
      <td>...</td>
      <td>5.094967e+10</td>
      <td>5.339986e+10</td>
      <td>4.966767e+10</td>
      <td>4.984325e+10</td>
      <td>5.400009e+10</td>
      <td>5.609719e+10</td>
      <td>6.009099e+10</td>
      <td>5.373453e+10</td>
      <td>6.496073e+10</td>
      <td>7.506795e+10</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2.398013e+10</td>
      <td>2.365180e+10</td>
      <td>2.289222e+10</td>
      <td>2.428285e+10</td>
      <td>2.625211e+10</td>
      <td>2.509067e+10</td>
      <td>2.793416e+10</td>
      <td>2.899389e+10</td>
      <td>3.209482e+10</td>
      <td>3.636104e+10</td>
      <td>...</td>
      <td>5.390195e+11</td>
      <td>5.478560e+11</td>
      <td>5.020848e+11</td>
      <td>5.057570e+11</td>
      <td>5.369245e+11</td>
      <td>5.524160e+11</td>
      <td>5.419492e+11</td>
      <td>5.470540e+11</td>
      <td>6.605305e+11</td>
      <td>8.991870e+11</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1.381140e+12</td>
      <td>1.446360e+12</td>
      <td>1.546370e+12</td>
      <td>1.670670e+12</td>
      <td>1.832620e+12</td>
      <td>1.994520e+12</td>
      <td>2.161640e+12</td>
      <td>2.308600e+12</td>
      <td>2.491800e+12</td>
      <td>2.745220e+12</td>
      <td>...</td>
      <td>7.771470e+13</td>
      <td>7.983720e+13</td>
      <td>7.528330e+13</td>
      <td>7.651900e+13</td>
      <td>8.148410e+13</td>
      <td>8.654270e+13</td>
      <td>8.777740e+13</td>
      <td>8.527270e+13</td>
      <td>9.715320e+13</td>
      <td>1.008800e+14</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 63 columns</p>
</div>




```python
df.info() # data types used of each column
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 266 entries, 0 to 265
    Data columns (total 65 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Country Name  266 non-null    object 
     1   Country Code  266 non-null    object 
     2   1960          126 non-null    float64
     3   1961          127 non-null    float64
     4   1962          128 non-null    float64
     5   1963          128 non-null    float64
     6   1964          128 non-null    float64
     7   1965          140 non-null    float64
     8   1966          143 non-null    float64
     9   1967          146 non-null    float64
     10  1968          151 non-null    float64
     11  1969          151 non-null    float64
     12  1970          160 non-null    float64
     13  1971          163 non-null    float64
     14  1972          163 non-null    float64
     15  1973          163 non-null    float64
     16  1974          164 non-null    float64
     17  1975          166 non-null    float64
     18  1976          167 non-null    float64
     19  1977          170 non-null    float64
     20  1978          169 non-null    float64
     21  1979          170 non-null    float64
     22  1980          183 non-null    float64
     23  1981          187 non-null    float64
     24  1982          189 non-null    float64
     25  1983          191 non-null    float64
     26  1984          193 non-null    float64
     27  1985          195 non-null    float64
     28  1986          197 non-null    float64
     29  1987          201 non-null    float64
     30  1988          207 non-null    float64
     31  1989          211 non-null    float64
     32  1990          226 non-null    float64
     33  1991          225 non-null    float64
     34  1992          228 non-null    float64
     35  1993          230 non-null    float64
     36  1994          232 non-null    float64
     37  1995          241 non-null    float64
     38  1996          241 non-null    float64
     39  1997          241 non-null    float64
     40  1998          242 non-null    float64
     41  1999          243 non-null    float64
     42  2000          247 non-null    float64
     43  2001          249 non-null    float64
     44  2002          254 non-null    float64
     45  2003          254 non-null    float64
     46  2004          254 non-null    float64
     47  2005          254 non-null    float64
     48  2006          255 non-null    float64
     49  2007          255 non-null    float64
     50  2008          256 non-null    float64
     51  2009          256 non-null    float64
     52  2010          257 non-null    float64
     53  2011          260 non-null    float64
     54  2012          258 non-null    float64
     55  2013          259 non-null    float64
     56  2014          260 non-null    float64
     57  2015          258 non-null    float64
     58  2016          258 non-null    float64
     59  2017          258 non-null    float64
     60  2018          258 non-null    float64
     61  2019          258 non-null    float64
     62  2020          257 non-null    float64
     63  2021          255 non-null    float64
     64  2022          242 non-null    float64
    dtypes: float64(63), object(2)
    memory usage: 135.2+ KB



```python
# df.corr() #correlation matrix between all the integer columns
```

### Data Selection


```python
df.iloc[251]  #select a particular 'row_num'
```




    Country Name       United States
    Country Code                 USA
    1960              543300000000.0
    1961              563300000000.0
    1962              605100000000.0
                          ...       
    2018            20533100000000.0
    2019            21381000000000.0
    2020            21060500000000.0
    2021            23315100000000.0
    2022            25439700000000.0
    Name: 251, Length: 65, dtype: object




```python
df["2022"] #select the particular 'col_name'
```




    0      3.544708e+09
    1      1.185140e+12
    2               NaN
    3      8.753940e+11
    4      1.067830e+11
               ...     
    261    9.409474e+09
    262             NaN
    263    4.052710e+11
    264    2.916378e+10
    265    2.736663e+10
    Name: 2022, Length: 266, dtype: float64




```python
df[["2000", "2022"]] #select multiple columns
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>2000</th>
      <th>2022</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.873453e+09</td>
      <td>3.544708e+09</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2.854040e+11</td>
      <td>1.185140e+12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1.401330e+11</td>
      <td>8.753940e+11</td>
    </tr>
    <tr>
      <th>4</th>
      <td>9.129595e+09</td>
      <td>1.067830e+11</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>261</th>
      <td>NaN</td>
      <td>9.409474e+09</td>
    </tr>
    <tr>
      <th>262</th>
      <td>9.679317e+09</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>263</th>
      <td>1.517530e+11</td>
      <td>4.052710e+11</td>
    </tr>
    <tr>
      <th>264</th>
      <td>3.600632e+09</td>
      <td>2.916378e+10</td>
    </tr>
    <tr>
      <th>265</th>
      <td>6.689958e+09</td>
      <td>2.736663e+10</td>
    </tr>
  </tbody>
</table>
<p>266 rows × 2 columns</p>
</div>



## Data Cleaning

These functions are used to handle the missing data. Some rows in the data contain some null and garbage values, which can hamper the performance of our trained model. So, it is always better to correct or remove these missing values.

- df.isnull(): This will identify the missing values in your dataframe.
- df.dropna(): This will remove the rows containing missing values in any column.
- df.fillna(val): This will fill the missing values with val given in the argument.
- df[col].astype(new_data_type): It can convert the data type of the selected columns to a different data type.


```python
df.fillna("-") # This will fill the missing values with val given in the argument
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country Name</th>
      <th>Country Code</th>
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aruba</td>
      <td>ABW</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>...</td>
      <td>2727849721.0</td>
      <td>2790849721.0</td>
      <td>2962907263.0</td>
      <td>2983635196.0</td>
      <td>3092429050.0</td>
      <td>3276184358.0</td>
      <td>3395798883.0</td>
      <td>2558906304.0</td>
      <td>3103184102.0</td>
      <td>3544707788.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Africa Eastern and Southern</td>
      <td>AFE</td>
      <td>18478095142.0</td>
      <td>19366314294.0</td>
      <td>20506467178.0</td>
      <td>22242734491.0</td>
      <td>24294329780.0</td>
      <td>26619560807.0</td>
      <td>28732792825.0</td>
      <td>31592963095.0</td>
      <td>...</td>
      <td>986343000000.0</td>
      <td>1006990000000.0</td>
      <td>932513000000.0</td>
      <td>890051000000.0</td>
      <td>1028390000000.0</td>
      <td>1012520000000.0</td>
      <td>1006190000000.0</td>
      <td>928880000000.0</td>
      <td>1086530000000.0</td>
      <td>1185140000000.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Afghanistan</td>
      <td>AFG</td>
      <td>537777811.1</td>
      <td>548888895.6</td>
      <td>546666677.8</td>
      <td>751111191.1</td>
      <td>800000044.4</td>
      <td>1006666638.0</td>
      <td>1399999967.0</td>
      <td>1673333418.0</td>
      <td>...</td>
      <td>20146416876.0</td>
      <td>20497128600.0</td>
      <td>19134221745.0</td>
      <td>18116572399.0</td>
      <td>18753456507.0</td>
      <td>18053222735.0</td>
      <td>18799444415.0</td>
      <td>19955929061.0</td>
      <td>14266499430.0</td>
      <td>-</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Africa Western and Central</td>
      <td>AFW</td>
      <td>10411646287.0</td>
      <td>11135924728.0</td>
      <td>11951712282.0</td>
      <td>12685805890.0</td>
      <td>13848998669.0</td>
      <td>14874755834.0</td>
      <td>15845575303.0</td>
      <td>14428492962.0</td>
      <td>...</td>
      <td>834097000000.0</td>
      <td>894505000000.0</td>
      <td>769263000000.0</td>
      <td>692115000000.0</td>
      <td>685630000000.0</td>
      <td>768158000000.0</td>
      <td>823406000000.0</td>
      <td>786962000000.0</td>
      <td>844928000000.0</td>
      <td>875394000000.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Angola</td>
      <td>AGO</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>...</td>
      <td>132339000000.0</td>
      <td>135967000000.0</td>
      <td>90496420626.0</td>
      <td>52761617226.0</td>
      <td>73690155047.0</td>
      <td>79450688232.0</td>
      <td>70897962713.0</td>
      <td>48501561230.0</td>
      <td>66505129989.0</td>
      <td>106783000000.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>261</th>
      <td>Kosovo</td>
      <td>XKX</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>...</td>
      <td>6735328610.0</td>
      <td>7074394735.0</td>
      <td>6295848423.0</td>
      <td>6682677290.0</td>
      <td>7180764703.0</td>
      <td>7878759715.0</td>
      <td>7899737577.0</td>
      <td>7717145218.0</td>
      <td>9412034299.0</td>
      <td>9409473518.0</td>
    </tr>
    <tr>
      <th>262</th>
      <td>Yemen, Rep.</td>
      <td>YEM</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>...</td>
      <td>40415233436.0</td>
      <td>43228585321.0</td>
      <td>42444489461.0</td>
      <td>31317824906.0</td>
      <td>26842228805.0</td>
      <td>21606160777.0</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
    </tr>
    <tr>
      <th>263</th>
      <td>South Africa</td>
      <td>ZAF</td>
      <td>8748596501.0</td>
      <td>9225996310.0</td>
      <td>9813996074.0</td>
      <td>10854195658.0</td>
      <td>11955995218.0</td>
      <td>13068994772.0</td>
      <td>14211394315.0</td>
      <td>15821393671.0</td>
      <td>...</td>
      <td>400886000000.0</td>
      <td>381199000000.0</td>
      <td>346710000000.0</td>
      <td>323586000000.0</td>
      <td>381449000000.0</td>
      <td>405261000000.0</td>
      <td>389330000000.0</td>
      <td>338291000000.0</td>
      <td>420118000000.0</td>
      <td>405271000000.0</td>
    </tr>
    <tr>
      <th>264</th>
      <td>Zambia</td>
      <td>ZMB</td>
      <td>713000000.0</td>
      <td>696285714.3</td>
      <td>693142857.1</td>
      <td>718714285.7</td>
      <td>839428571.4</td>
      <td>1082857143.0</td>
      <td>1264285714.0</td>
      <td>1368000000.0</td>
      <td>...</td>
      <td>28037239463.0</td>
      <td>27141023558.0</td>
      <td>21251216799.0</td>
      <td>20958412538.0</td>
      <td>25873601261.0</td>
      <td>26311507274.0</td>
      <td>23308667781.0</td>
      <td>18110638269.0</td>
      <td>22096416934.0</td>
      <td>29163782138.0</td>
    </tr>
    <tr>
      <th>265</th>
      <td>Zimbabwe</td>
      <td>ZWE</td>
      <td>1052990400.0</td>
      <td>1096646600.0</td>
      <td>1117601600.0</td>
      <td>1159511700.0</td>
      <td>1217138000.0</td>
      <td>1311435800.0</td>
      <td>1281749500.0</td>
      <td>1397002000.0</td>
      <td>...</td>
      <td>19091020000.0</td>
      <td>19495519600.0</td>
      <td>19963120600.0</td>
      <td>20548678100.0</td>
      <td>17584890937.0</td>
      <td>34156069918.0</td>
      <td>21832234921.0</td>
      <td>21509698407.0</td>
      <td>28371238666.0</td>
      <td>27366627153.0</td>
    </tr>
  </tbody>
</table>
<p>266 rows × 65 columns</p>
</div>



## Data Analysis

Here, we will use some helpful functions in data analysis, like grouping, sorting, and filtering.

**Aggregation Functions:**
You can group a column by its name and then apply some aggregation functions like sum, min/max, mean, etc.

df.groupby("col_name_1").agg({"col_name_2": "sum"})


```python

```
