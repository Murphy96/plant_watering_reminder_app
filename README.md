# Hello! 
This is an app prototype in with ingestion pipelines in Python, SQL ETL data warehouse architecture, and data algorithms, orchestration function, in Python. This app uses a users' county to pull current and foretasted weather data from the National Weather Service API, 
historical data from NCEI, the warehouse ETL to remake rainfall data that used to be aggregated within the NWS pipeline but is since broken, then runs an algorithm in Python to determine if an outdoor garden needs to be watered based on temperature and precipitation history and forecast, then sends an email to user if the garden needs to be watered.

## Design 


### Design subject to change as more hiccups in data are found 

### main.py (orchestration function)

### 1) User Input Validation & Transformation (user_validation.py)
This file will take user inputs, validate them, and return the inputs required for the API call for weather data and the cleaned and standardized email address. 

### 2) Weather Data API Call & Weather Object Creation (weather.py)
This file will take the outputs from file 1, make the API call to the National Weather Service API, read the returned JSON object, and 
create a dataframe with only the average high temperatures for the week and the total precipitation for the week as the output.    

### 3) To Water or Not to Water? That is the Question. (watering.py)
This file will take the output of weather.py and create the algorithm that returns a Boolean if one needs to water their outside plants. 
This algorithm will be simple, but may eventually include more inputs such as presence of mulch, overcast/sunny, types of plants etc. 

### 4) Let's Send an Email. (email.py)
If True is returned in watering.py, send an email to the user. 

### 5) Test it Out (tests.py) 
Tests for 1-4 to ensure everything is running smoothly. 
