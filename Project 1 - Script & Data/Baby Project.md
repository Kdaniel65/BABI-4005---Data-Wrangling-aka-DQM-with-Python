# Baby Project: Exploring the Social Media vs Productivity Dataset

## What kind of data analysis?
Look at the data, and in your markdown cells, explain what the data looks like.
- Create some summaries 
- Create some graphs!
- Explain a few things.  When I read this, I should understand something about this dataset.


## Part 1: Importing Libraries 

I am using three libraries: 
- pandas
- matplotlib.plyplot
- seaborn


```python
#Import pandas, matppotlib, and seaborn libraries
import pandas as pd 
import matplotlib.pyplot as plt
import seaborn as sns 


#Display plots directly below the code cell 
%matplotlib inline
```

### Part 2: Loading and Exploring the Dataset


```python
# Load the dataset
df = pd.read_csv('social_media_vs_productivity.csv')

# View the first 30 rows
df.head(30)
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
      <th>age</th>
      <th>gender</th>
      <th>job_type</th>
      <th>daily_social_media_time</th>
      <th>social_platform_preference</th>
      <th>number_of_notifications</th>
      <th>work_hours_per_day</th>
      <th>perceived_productivity_score</th>
      <th>actual_productivity_score</th>
      <th>stress_level</th>
      <th>sleep_hours</th>
      <th>screen_time_before_sleep</th>
      <th>breaks_during_work</th>
      <th>uses_focus_apps</th>
      <th>has_digital_wellbeing_enabled</th>
      <th>coffee_consumption_per_day</th>
      <th>days_feeling_burnout_per_month</th>
      <th>weekly_offline_hours</th>
      <th>job_satisfaction_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>56</td>
      <td>Male</td>
      <td>Unemployed</td>
      <td>4.180940</td>
      <td>Facebook</td>
      <td>61</td>
      <td>6.753558</td>
      <td>8.040464</td>
      <td>7.291555</td>
      <td>4.0</td>
      <td>5.116546</td>
      <td>0.419102</td>
      <td>8</td>
      <td>False</td>
      <td>False</td>
      <td>4</td>
      <td>11</td>
      <td>21.927072</td>
      <td>6.336688</td>
    </tr>
    <tr>
      <th>1</th>
      <td>46</td>
      <td>Male</td>
      <td>Health</td>
      <td>3.249603</td>
      <td>Twitter</td>
      <td>59</td>
      <td>9.169296</td>
      <td>5.063368</td>
      <td>5.165093</td>
      <td>7.0</td>
      <td>5.103897</td>
      <td>0.671519</td>
      <td>7</td>
      <td>True</td>
      <td>True</td>
      <td>2</td>
      <td>25</td>
      <td>0.000000</td>
      <td>3.412427</td>
    </tr>
    <tr>
      <th>2</th>
      <td>32</td>
      <td>Male</td>
      <td>Finance</td>
      <td>NaN</td>
      <td>Twitter</td>
      <td>57</td>
      <td>7.910952</td>
      <td>3.861762</td>
      <td>3.474053</td>
      <td>4.0</td>
      <td>8.583222</td>
      <td>0.624378</td>
      <td>0</td>
      <td>True</td>
      <td>False</td>
      <td>3</td>
      <td>17</td>
      <td>10.322044</td>
      <td>2.474944</td>
    </tr>
    <tr>
      <th>3</th>
      <td>60</td>
      <td>Female</td>
      <td>Unemployed</td>
      <td>NaN</td>
      <td>Facebook</td>
      <td>59</td>
      <td>6.355027</td>
      <td>2.916331</td>
      <td>1.774869</td>
      <td>6.0</td>
      <td>6.052984</td>
      <td>1.204540</td>
      <td>1</td>
      <td>False</td>
      <td>False</td>
      <td>0</td>
      <td>4</td>
      <td>23.876616</td>
      <td>1.733670</td>
    </tr>
    <tr>
      <th>4</th>
      <td>25</td>
      <td>Male</td>
      <td>IT</td>
      <td>NaN</td>
      <td>Telegram</td>
      <td>66</td>
      <td>6.214096</td>
      <td>8.868753</td>
      <td>NaN</td>
      <td>7.0</td>
      <td>5.405706</td>
      <td>1.876254</td>
      <td>1</td>
      <td>False</td>
      <td>True</td>
      <td>1</td>
      <td>30</td>
      <td>10.653519</td>
      <td>9.693060</td>
    </tr>
    <tr>
      <th>5</th>
      <td>38</td>
      <td>Male</td>
      <td>Finance</td>
      <td>1.512568</td>
      <td>Twitter</td>
      <td>50</td>
      <td>6.429312</td>
      <td>NaN</td>
      <td>4.081026</td>
      <td>5.0</td>
      <td>5.515251</td>
      <td>1.518612</td>
      <td>5</td>
      <td>False</td>
      <td>True</td>
      <td>5</td>
      <td>2</td>
      <td>0.000000</td>
      <td>4.568728</td>
    </tr>
    <tr>
      <th>6</th>
      <td>56</td>
      <td>Female</td>
      <td>Unemployed</td>
      <td>4.381070</td>
      <td>TikTok</td>
      <td>60</td>
      <td>3.902309</td>
      <td>6.420989</td>
      <td>5.976408</td>
      <td>7.0</td>
      <td>7.549849</td>
      <td>2.252624</td>
      <td>4</td>
      <td>False</td>
      <td>False</td>
      <td>4</td>
      <td>20</td>
      <td>24.084905</td>
      <td>5.501373</td>
    </tr>
    <tr>
      <th>7</th>
      <td>36</td>
      <td>Female</td>
      <td>Education</td>
      <td>4.089168</td>
      <td>Twitter</td>
      <td>49</td>
      <td>6.560467</td>
      <td>2.681830</td>
      <td>2.446927</td>
      <td>4.0</td>
      <td>6.325507</td>
      <td>0.747998</td>
      <td>2</td>
      <td>False</td>
      <td>False</td>
      <td>4</td>
      <td>29</td>
      <td>8.419648</td>
      <td>3.444376</td>
    </tr>
    <tr>
      <th>8</th>
      <td>40</td>
      <td>Female</td>
      <td>Education</td>
      <td>4.097401</td>
      <td>Instagram</td>
      <td>57</td>
      <td>5.839590</td>
      <td>3.219022</td>
      <td>3.004240</td>
      <td>4.0</td>
      <td>NaN</td>
      <td>0.000000</td>
      <td>10</td>
      <td>False</td>
      <td>True</td>
      <td>2</td>
      <td>10</td>
      <td>0.000000</td>
      <td>1.960131</td>
    </tr>
    <tr>
      <th>9</th>
      <td>28</td>
      <td>Other</td>
      <td>IT</td>
      <td>7.595577</td>
      <td>Twitter</td>
      <td>64</td>
      <td>5.888936</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.0</td>
      <td>6.761952</td>
      <td>1.449841</td>
      <td>10</td>
      <td>False</td>
      <td>False</td>
      <td>1</td>
      <td>18</td>
      <td>6.959377</td>
      <td>6.808102</td>
    </tr>
    <tr>
      <th>10</th>
      <td>28</td>
      <td>Male</td>
      <td>IT</td>
      <td>3.341559</td>
      <td>Twitter</td>
      <td>57</td>
      <td>11.022035</td>
      <td>8.940636</td>
      <td>7.983252</td>
      <td>4.0</td>
      <td>3.952547</td>
      <td>1.028640</td>
      <td>5</td>
      <td>True</td>
      <td>True</td>
      <td>1</td>
      <td>3</td>
      <td>13.514515</td>
      <td>9.414637</td>
    </tr>
    <tr>
      <th>11</th>
      <td>41</td>
      <td>Female</td>
      <td>Finance</td>
      <td>2.200061</td>
      <td>Twitter</td>
      <td>59</td>
      <td>10.147732</td>
      <td>7.696546</td>
      <td>NaN</td>
      <td>9.0</td>
      <td>6.091283</td>
      <td>0.889256</td>
      <td>8</td>
      <td>True</td>
      <td>False</td>
      <td>4</td>
      <td>30</td>
      <td>8.732449</td>
      <td>6.028926</td>
    </tr>
    <tr>
      <th>12</th>
      <td>53</td>
      <td>Male</td>
      <td>Student</td>
      <td>2.715760</td>
      <td>TikTok</td>
      <td>77</td>
      <td>5.637154</td>
      <td>8.575504</td>
      <td>7.715133</td>
      <td>NaN</td>
      <td>4.559258</td>
      <td>0.599293</td>
      <td>5</td>
      <td>False</td>
      <td>False</td>
      <td>0</td>
      <td>15</td>
      <td>4.956755</td>
      <td>8.770683</td>
    </tr>
    <tr>
      <th>13</th>
      <td>57</td>
      <td>Male</td>
      <td>Education</td>
      <td>0.000000</td>
      <td>Twitter</td>
      <td>60</td>
      <td>6.822442</td>
      <td>8.850758</td>
      <td>7.930675</td>
      <td>5.0</td>
      <td>6.764830</td>
      <td>1.341070</td>
      <td>3</td>
      <td>False</td>
      <td>False</td>
      <td>4</td>
      <td>27</td>
      <td>18.052656</td>
      <td>7.563358</td>
    </tr>
    <tr>
      <th>14</th>
      <td>41</td>
      <td>Male</td>
      <td>Education</td>
      <td>3.773326</td>
      <td>TikTok</td>
      <td>65</td>
      <td>8.636782</td>
      <td>7.511934</td>
      <td>6.773923</td>
      <td>10.0</td>
      <td>7.921161</td>
      <td>1.263446</td>
      <td>6</td>
      <td>True</td>
      <td>False</td>
      <td>4</td>
      <td>20</td>
      <td>12.767974</td>
      <td>6.849160</td>
    </tr>
    <tr>
      <th>15</th>
      <td>20</td>
      <td>Male</td>
      <td>Student</td>
      <td>5.826311</td>
      <td>TikTok</td>
      <td>67</td>
      <td>4.718497</td>
      <td>2.645825</td>
      <td>2.861171</td>
      <td>5.0</td>
      <td>8.301198</td>
      <td>1.087081</td>
      <td>9</td>
      <td>False</td>
      <td>False</td>
      <td>4</td>
      <td>0</td>
      <td>8.095881</td>
      <td>2.179692</td>
    </tr>
    <tr>
      <th>16</th>
      <td>39</td>
      <td>Male</td>
      <td>Finance</td>
      <td>2.305803</td>
      <td>Twitter</td>
      <td>64</td>
      <td>7.050821</td>
      <td>6.983516</td>
      <td>6.629587</td>
      <td>9.0</td>
      <td>4.847608</td>
      <td>0.070189</td>
      <td>2</td>
      <td>False</td>
      <td>False</td>
      <td>3</td>
      <td>9</td>
      <td>12.110620</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>17</th>
      <td>19</td>
      <td>Male</td>
      <td>Health</td>
      <td>5.621220</td>
      <td>Twitter</td>
      <td>52</td>
      <td>8.201916</td>
      <td>2.154417</td>
      <td>2.062080</td>
      <td>1.0</td>
      <td>5.223211</td>
      <td>1.957239</td>
      <td>3</td>
      <td>False</td>
      <td>False</td>
      <td>2</td>
      <td>6</td>
      <td>20.032649</td>
      <td>1.731725</td>
    </tr>
    <tr>
      <th>18</th>
      <td>41</td>
      <td>Female</td>
      <td>Health</td>
      <td>NaN</td>
      <td>Twitter</td>
      <td>47</td>
      <td>8.618984</td>
      <td>8.515498</td>
      <td>7.428871</td>
      <td>5.0</td>
      <td>6.275959</td>
      <td>0.000000</td>
      <td>2</td>
      <td>False</td>
      <td>False</td>
      <td>2</td>
      <td>26</td>
      <td>0.229511</td>
      <td>5.590406</td>
    </tr>
    <tr>
      <th>19</th>
      <td>61</td>
      <td>Female</td>
      <td>Education</td>
      <td>1.445358</td>
      <td>Twitter</td>
      <td>62</td>
      <td>6.419898</td>
      <td>6.873341</td>
      <td>5.957137</td>
      <td>6.0</td>
      <td>6.975413</td>
      <td>0.000000</td>
      <td>4</td>
      <td>True</td>
      <td>True</td>
      <td>3</td>
      <td>17</td>
      <td>14.088959</td>
      <td>5.442305</td>
    </tr>
    <tr>
      <th>20</th>
      <td>47</td>
      <td>Other</td>
      <td>Health</td>
      <td>1.437666</td>
      <td>TikTok</td>
      <td>63</td>
      <td>7.610461</td>
      <td>7.832933</td>
      <td>6.969125</td>
      <td>7.0</td>
      <td>5.399601</td>
      <td>1.035228</td>
      <td>10</td>
      <td>False</td>
      <td>False</td>
      <td>2</td>
      <td>22</td>
      <td>3.565713</td>
      <td>6.490481</td>
    </tr>
    <tr>
      <th>21</th>
      <td>55</td>
      <td>Female</td>
      <td>Finance</td>
      <td>0.071503</td>
      <td>TikTok</td>
      <td>50</td>
      <td>7.093237</td>
      <td>8.968751</td>
      <td>8.119665</td>
      <td>5.0</td>
      <td>5.223283</td>
      <td>0.880365</td>
      <td>2</td>
      <td>False</td>
      <td>False</td>
      <td>1</td>
      <td>21</td>
      <td>4.720501</td>
      <td>8.548482</td>
    </tr>
    <tr>
      <th>22</th>
      <td>19</td>
      <td>Male</td>
      <td>Health</td>
      <td>5.916044</td>
      <td>Twitter</td>
      <td>65</td>
      <td>6.592757</td>
      <td>3.873519</td>
      <td>2.974137</td>
      <td>5.0</td>
      <td>5.546582</td>
      <td>0.829939</td>
      <td>1</td>
      <td>False</td>
      <td>False</td>
      <td>2</td>
      <td>22</td>
      <td>10.619489</td>
      <td>3.207401</td>
    </tr>
    <tr>
      <th>23</th>
      <td>38</td>
      <td>Male</td>
      <td>IT</td>
      <td>4.030315</td>
      <td>TikTok</td>
      <td>57</td>
      <td>6.299842</td>
      <td>6.851403</td>
      <td>6.073044</td>
      <td>7.0</td>
      <td>5.006478</td>
      <td>1.260447</td>
      <td>6</td>
      <td>True</td>
      <td>False</td>
      <td>1</td>
      <td>13</td>
      <td>14.251701</td>
      <td>5.784979</td>
    </tr>
    <tr>
      <th>24</th>
      <td>50</td>
      <td>Male</td>
      <td>Finance</td>
      <td>4.242185</td>
      <td>Instagram</td>
      <td>58</td>
      <td>5.068889</td>
      <td>2.428811</td>
      <td>1.438418</td>
      <td>NaN</td>
      <td>7.707291</td>
      <td>0.348540</td>
      <td>7</td>
      <td>True</td>
      <td>False</td>
      <td>2</td>
      <td>14</td>
      <td>14.331847</td>
      <td>0.842077</td>
    </tr>
    <tr>
      <th>25</th>
      <td>29</td>
      <td>Male</td>
      <td>Student</td>
      <td>1.551556</td>
      <td>Telegram</td>
      <td>52</td>
      <td>7.965374</td>
      <td>8.564363</td>
      <td>7.209460</td>
      <td>3.0</td>
      <td>6.711047</td>
      <td>0.772266</td>
      <td>8</td>
      <td>False</td>
      <td>False</td>
      <td>0</td>
      <td>22</td>
      <td>6.724090</td>
      <td>7.587604</td>
    </tr>
    <tr>
      <th>26</th>
      <td>39</td>
      <td>Female</td>
      <td>Education</td>
      <td>4.593419</td>
      <td>Facebook</td>
      <td>73</td>
      <td>10.619575</td>
      <td>3.230612</td>
      <td>3.660009</td>
      <td>2.0</td>
      <td>6.773534</td>
      <td>1.961318</td>
      <td>5</td>
      <td>True</td>
      <td>False</td>
      <td>0</td>
      <td>15</td>
      <td>16.921902</td>
      <td>4.416550</td>
    </tr>
    <tr>
      <th>27</th>
      <td>61</td>
      <td>Female</td>
      <td>Finance</td>
      <td>1.984596</td>
      <td>Telegram</td>
      <td>56</td>
      <td>5.983900</td>
      <td>5.981160</td>
      <td>5.672383</td>
      <td>3.0</td>
      <td>NaN</td>
      <td>0.687990</td>
      <td>10</td>
      <td>True</td>
      <td>False</td>
      <td>0</td>
      <td>9</td>
      <td>0.690294</td>
      <td>5.181730</td>
    </tr>
    <tr>
      <th>28</th>
      <td>42</td>
      <td>Male</td>
      <td>Health</td>
      <td>2.076693</td>
      <td>Telegram</td>
      <td>57</td>
      <td>8.254002</td>
      <td>5.140098</td>
      <td>4.767332</td>
      <td>3.0</td>
      <td>3.000000</td>
      <td>1.560576</td>
      <td>0</td>
      <td>True</td>
      <td>True</td>
      <td>2</td>
      <td>0</td>
      <td>16.438964</td>
      <td>6.176500</td>
    </tr>
    <tr>
      <th>29</th>
      <td>44</td>
      <td>Male</td>
      <td>Finance</td>
      <td>5.144763</td>
      <td>Facebook</td>
      <td>55</td>
      <td>8.096872</td>
      <td>2.218581</td>
      <td>2.416909</td>
      <td>NaN</td>
      <td>5.009060</td>
      <td>1.748973</td>
      <td>0</td>
      <td>False</td>
      <td>False</td>
      <td>0</td>
      <td>24</td>
      <td>5.104789</td>
      <td>0.518372</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.shape
```




    (30000, 19)




```python
# Showing the Summary Stats
df.describe(include='all').round(2)
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
      <th>age</th>
      <th>gender</th>
      <th>job_type</th>
      <th>daily_social_media_time</th>
      <th>social_platform_preference</th>
      <th>number_of_notifications</th>
      <th>work_hours_per_day</th>
      <th>perceived_productivity_score</th>
      <th>actual_productivity_score</th>
      <th>stress_level</th>
      <th>sleep_hours</th>
      <th>screen_time_before_sleep</th>
      <th>breaks_during_work</th>
      <th>uses_focus_apps</th>
      <th>has_digital_wellbeing_enabled</th>
      <th>coffee_consumption_per_day</th>
      <th>days_feeling_burnout_per_month</th>
      <th>weekly_offline_hours</th>
      <th>job_satisfaction_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>30000.00</td>
      <td>30000</td>
      <td>30000</td>
      <td>27235.00</td>
      <td>30000</td>
      <td>30000.00</td>
      <td>30000.00</td>
      <td>28386.00</td>
      <td>27635.00</td>
      <td>28096.00</td>
      <td>27402.00</td>
      <td>27789.00</td>
      <td>30000.00</td>
      <td>30000</td>
      <td>30000</td>
      <td>30000.00</td>
      <td>30000.00</td>
      <td>30000.00</td>
      <td>27270.00</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>NaN</td>
      <td>3</td>
      <td>6</td>
      <td>NaN</td>
      <td>5</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>top</th>
      <td>NaN</td>
      <td>Male</td>
      <td>Education</td>
      <td>NaN</td>
      <td>TikTok</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>False</td>
      <td>False</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>NaN</td>
      <td>14452</td>
      <td>5055</td>
      <td>NaN</td>
      <td>6096</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20979</td>
      <td>22602</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>41.49</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.11</td>
      <td>NaN</td>
      <td>59.96</td>
      <td>6.99</td>
      <td>5.51</td>
      <td>4.95</td>
      <td>5.51</td>
      <td>6.50</td>
      <td>1.03</td>
      <td>4.99</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.00</td>
      <td>15.56</td>
      <td>10.36</td>
      <td>4.96</td>
    </tr>
    <tr>
      <th>std</th>
      <td>13.84</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.07</td>
      <td>NaN</td>
      <td>7.72</td>
      <td>2.00</td>
      <td>2.02</td>
      <td>1.88</td>
      <td>2.87</td>
      <td>1.46</td>
      <td>0.65</td>
      <td>3.17</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.41</td>
      <td>9.25</td>
      <td>7.28</td>
      <td>2.12</td>
    </tr>
    <tr>
      <th>min</th>
      <td>18.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.00</td>
      <td>NaN</td>
      <td>30.00</td>
      <td>0.00</td>
      <td>2.00</td>
      <td>0.30</td>
      <td>1.00</td>
      <td>3.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
      <td>0.00</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>30.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.64</td>
      <td>NaN</td>
      <td>55.00</td>
      <td>5.64</td>
      <td>3.76</td>
      <td>3.37</td>
      <td>3.00</td>
      <td>5.49</td>
      <td>0.53</td>
      <td>2.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.00</td>
      <td>8.00</td>
      <td>4.54</td>
      <td>3.36</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>41.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.03</td>
      <td>NaN</td>
      <td>60.00</td>
      <td>6.99</td>
      <td>5.53</td>
      <td>4.95</td>
      <td>6.00</td>
      <td>6.50</td>
      <td>1.01</td>
      <td>5.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.00</td>
      <td>16.00</td>
      <td>10.01</td>
      <td>4.95</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>53.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>4.37</td>
      <td>NaN</td>
      <td>65.00</td>
      <td>8.35</td>
      <td>7.27</td>
      <td>6.53</td>
      <td>8.00</td>
      <td>7.50</td>
      <td>1.48</td>
      <td>8.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.00</td>
      <td>24.00</td>
      <td>15.30</td>
      <td>6.58</td>
    </tr>
    <tr>
      <th>max</th>
      <td>65.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>17.97</td>
      <td>NaN</td>
      <td>90.00</td>
      <td>12.00</td>
      <td>9.00</td>
      <td>9.85</td>
      <td>10.00</td>
      <td>10.00</td>
      <td>3.00</td>
      <td>10.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>10.00</td>
      <td>31.00</td>
      <td>40.96</td>
      <td>10.00</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Checking the number of null values
df.isnull().sum()
```




    age                                  0
    gender                               0
    job_type                             0
    daily_social_media_time           2765
    social_platform_preference           0
    number_of_notifications              0
    work_hours_per_day                   0
    perceived_productivity_score      1614
    actual_productivity_score         2365
    stress_level                      1904
    sleep_hours                       2598
    screen_time_before_sleep          2211
    breaks_during_work                   0
    uses_focus_apps                      0
    has_digital_wellbeing_enabled        0
    coffee_consumption_per_day           0
    days_feeling_burnout_per_month       0
    weekly_offline_hours                 0
    job_satisfaction_score            2730
    dtype: int64



### Dataset Observations:

This dataset contains 30,000 records and 19 columns. 

This dataset has collected multiple records that cover the following topics: 
- Demographics
- Social Media Usage
- Work Productivity
- Personal Health

Observations:
- Several columns have missing values:
    - daily_social_media_time           2765
    - perceived_productivity_score      1614
    - actual_productivity_score         2365
    - stress_level                      1904
    - sleep_hours                       2598
    - screen_time_before_sleep          2211
    - job_satisfaction_score            2730
- There are 6 different job types: Unemployed, Health, Finance, IT, Education, and Student
- Social media time ranges from 0 to about 18 hours per day
- Productivity scores range from 0 to 10
- Work Hours per day ranges from 0 to 12


## Part 3: Creating Summaries

We are going to explore the relationship between the job types, daily social media time, perceived productivity and actual productivity


```python
# Grouping by job type and comparing daily social media time, perceived productivity scores and actual productivity scores
df.groupby("job_type").agg({
    "daily_social_media_time": ['min', 'max', 'mean', 'std', 'count'],
    "perceived_productivity_score": ['min', 'max', 'mean', 'std', 'count'],
    "actual_productivity_score": ['min', 'max', 'mean', 'std', 'count']
}).round(2)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="5" halign="left">daily_social_media_time</th>
      <th colspan="5" halign="left">perceived_productivity_score</th>
      <th colspan="5" halign="left">actual_productivity_score</th>
    </tr>
    <tr>
      <th></th>
      <th>min</th>
      <th>max</th>
      <th>mean</th>
      <th>std</th>
      <th>count</th>
      <th>min</th>
      <th>max</th>
      <th>mean</th>
      <th>std</th>
      <th>count</th>
      <th>min</th>
      <th>max</th>
      <th>mean</th>
      <th>std</th>
      <th>count</th>
    </tr>
    <tr>
      <th>job_type</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Education</th>
      <td>0.0</td>
      <td>17.75</td>
      <td>3.10</td>
      <td>2.04</td>
      <td>4591</td>
      <td>2.0</td>
      <td>9.0</td>
      <td>5.49</td>
      <td>2.03</td>
      <td>4779</td>
      <td>0.52</td>
      <td>9.66</td>
      <td>4.93</td>
      <td>1.89</td>
      <td>4667</td>
    </tr>
    <tr>
      <th>Finance</th>
      <td>0.0</td>
      <td>17.73</td>
      <td>3.08</td>
      <td>2.07</td>
      <td>4546</td>
      <td>2.0</td>
      <td>9.0</td>
      <td>5.51</td>
      <td>2.04</td>
      <td>4757</td>
      <td>0.53</td>
      <td>9.36</td>
      <td>4.97</td>
      <td>1.90</td>
      <td>4639</td>
    </tr>
    <tr>
      <th>Health</th>
      <td>0.0</td>
      <td>17.21</td>
      <td>3.07</td>
      <td>2.02</td>
      <td>4480</td>
      <td>2.0</td>
      <td>9.0</td>
      <td>5.48</td>
      <td>2.04</td>
      <td>4662</td>
      <td>0.62</td>
      <td>9.38</td>
      <td>4.92</td>
      <td>1.90</td>
      <td>4540</td>
    </tr>
    <tr>
      <th>IT</th>
      <td>0.0</td>
      <td>17.82</td>
      <td>3.13</td>
      <td>2.06</td>
      <td>4542</td>
      <td>2.0</td>
      <td>9.0</td>
      <td>5.56</td>
      <td>2.02</td>
      <td>4741</td>
      <td>0.30</td>
      <td>9.85</td>
      <td>5.01</td>
      <td>1.88</td>
      <td>4618</td>
    </tr>
    <tr>
      <th>Student</th>
      <td>0.0</td>
      <td>17.86</td>
      <td>3.14</td>
      <td>2.12</td>
      <td>4572</td>
      <td>2.0</td>
      <td>9.0</td>
      <td>5.48</td>
      <td>2.02</td>
      <td>4752</td>
      <td>0.60</td>
      <td>9.09</td>
      <td>4.90</td>
      <td>1.88</td>
      <td>4616</td>
    </tr>
    <tr>
      <th>Unemployed</th>
      <td>0.0</td>
      <td>17.97</td>
      <td>3.16</td>
      <td>2.14</td>
      <td>4504</td>
      <td>2.0</td>
      <td>9.0</td>
      <td>5.54</td>
      <td>1.99</td>
      <td>4695</td>
      <td>0.30</td>
      <td>9.15</td>
      <td>4.99</td>
      <td>1.85</td>
      <td>4555</td>
    </tr>
  </tbody>
</table>
</div>



## Part 4: Visualization

We are going to visualize the relationship between the job types, daily social media time, perceived productivity and actual productivity


```python
## Perceived vs Actual Productivity Score by Job Type Scatterplot
plt.figure(figsize=(10, 6))
sns.scatterplot(x="perceived_productivity_score", y="actual_productivity_score", 
                hue="job_type", data=df, palette="Set1", alpha=0.6)
plt.title("Perceived vs Actual Productivity Score by Job Type")
plt.xlabel("Perceived Productivity Score")
plt.ylabel("Actual Productivity Score")
plt.grid(True, alpha=0.3)
plt.legend(title="Job Type", bbox_to_anchor=(1.05, 1), loc='upper left')
plt.show()
```


    
![png](output_13_0.png)
    



```python
## Average Productivity Scores By Job Type Bar chart  
productivity_by_job = df.groupby("job_type")[["perceived_productivity_score", 
                                                "actual_productivity_score"]].mean()

plt.figure(figsize=(10, 6))
productivity_by_job.plot(kind='bar', color=['blue', 'yellow'], edgecolor='black')
plt.title("Average Productivity Scores by Job Type")
plt.xlabel("Job Type")
plt.ylabel("Average Score")
plt.xticks(rotation=45)
plt.legend(["Perceived Productivity", "Actual Productivity"])
plt.grid(axis='y', alpha=0.3)
plt.show()
```


    <Figure size 1000x600 with 0 Axes>



    
![png](output_14_1.png)
    



```python
## Social Media Time vs Actual Productivity by Job Type - Scatterplot for each 
job_types = df['job_type'].unique()

fig, axes = plt.subplots(2, 3, figsize=(15, 10))
axes = axes.flatten()

for i, job in enumerate(job_types):
    job_data = df[df['job_type'] == job]
    axes[i].scatter(job_data['daily_social_media_time'], 
                   job_data['actual_productivity_score'], 
                   alpha=0.5, color=sns.color_palette('Set1', len(job_types))[i])
    axes[i].set_title(f'{job}')
    axes[i].set_xlabel('Daily Social Media Time (hours)')
    axes[i].set_ylabel('Actual Productivity Score')
    axes[i].grid(True, alpha=0.3)

plt.suptitle('Social Media Time vs Actual Productivity by Job Type', fontsize=14, y=1.00)
plt.tight_layout()
plt.show()
```


    
![png](output_15_0.png)
    


## Part 5: Analysis Insights

Based on the summaries and visualizations, here are my insights about the productivity patterns of the dataset:

- There seems to be a consistent relationship that an individuals' perceived productivity on average slightly over estimates their actual productivity
- This could mean that people estimate their own productivity relatively accurately 
- The summaries reveal there is no conclusive relationship between Daily Social Media Time and Actual Productivity Score  
- Although I am thoroughly impressed by the person who works in education, spent more than 17.5 hours in a day on social media and had an actual productivity score above 8 (this is an outlier and could be an entry error)
