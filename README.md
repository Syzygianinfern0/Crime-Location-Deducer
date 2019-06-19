# Crime-Location-Deducer
Generates Redacted Latitudes and Longitudes of missing entries. Task 1 of my Spider Inductions for the Summer of '19
### Code Stack
* numpy - matrix manipulations
* folium - map generator
* matplotlib - pyplots visualisation
* pandas - dataset handler
* seaborn - correlations and 
  
# Problem Statement:
The Chicago Police Department's CLEAR (Citizen Law Enforcement Analysis and Reporting) system has lost the locations of some of the crimes in Chicago. They need an approximate location of the crime from the remaining data. The dataset is available with the police department and it reflects reported incidents of crime (with the exception of murders where data exists for each victim) that occurred in the City of Chicago from 2012 to 2017.

For the lost locations the related data to those locations is still with Police Department. You are given the data related to lost locations of the city. Your task is to predict the exact location of the Crime by the help Neural Networks algorithm.

# Files and Folders:
The original dataset can be taken from [here](https://drive.google.com/drive/folders/12JgRDsv460rR5atQw2Bha0M0UGSd99Ip) or directly from [Kaggle](https://www.kaggle.com/currie32/crimes-in-chicago)
* `Crime Location Deducer.ipynb` - The notebook corresponding to the code.
* `assets` - Some Images
* `Final` - Has the train, test, validation data which has been organised
* `Weights` - Trained model's Weights

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
