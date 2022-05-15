# date_gas_light
A CSV file containing the average daily prices of natural gas and electricity in Spain. The separator is ";". The prices are rounded to two decimal places. 

2017-2022_date_gas_light.csv contains three colums: "Date";"GasEUR/MWH";"LightEUR/MWH". It is easily pandable with:

    import pandas as pd
    import numpy as np

    data = pd.read_csv("2017-2022_date_gas_light.csv", sep=";", parse_dates=["Date"])
    
There is a correlation between the two variables (R = 0.6), though recent years have gotten more chaotic.
