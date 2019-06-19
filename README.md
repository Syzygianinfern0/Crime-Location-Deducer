# Crime-Location-Deducer
Generates Redacted Latitudes and Longitudes of missing entries. Task 1 of my Spider Inductions for the Summer of '19
### Code Stack
* numpy - matrix manipulations
* folium - map generator
* matplotlib - pyplots visualisation
* pandas - dataset handler
* seaborn - correlations and heatmaps

# Files and Folders:
* assets - Some Images
* Final - Has the train, test, validation data which has been organised
* Weights - Trained model's Weights
* S P Sharan.ipynb - The notebook corresponding to the code.

# Notes to User:
* The model if to be tested by anyone, I recommend to start from the "Scaling and Normalisation" part where the assets are loaded in and can proceed from there to satisfy all dependencies. 
* Any external dataset if to be used must follow all manipulations undergone by the train/test/validation data. It's pretty easy to port the code as required as everything is modular and functions exist for all tasks

# Result
The below function use absolute tolerance and relative tolerance to measure the closeness between float objects. The model achieved a very good result with only 26 predictions having an error above 0.45% out of about 3 lakhs samples!!! 👌👌

This suggests that our model is so accurate that it can almost be used in real world application!!


```python
truth = np.isclose(revert(y_prediction),
                   revert(y_val),
                   atol=0.1,
                   rtol=0.0045)
len(np.where(truth == False)[0])

>>> 26
```
