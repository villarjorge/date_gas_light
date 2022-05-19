# Spanish prices of natural gas and electricity
A CSV file containing the average daily prices of natural gas and electricity in Spain. The dates go from 2017-01-01 to 2022-04-27. The separator is ";". The prices are rounded to two decimal places. 

2017-2022_date_gas_light.csv contains three colums: "Date";"GasEUR/MWH";"LightEUR/MWH". It is easily pandable with:

    import pandas as pd
    import numpy as np

    data = pd.read_csv("2017-2022_date_gas_light.csv", sep=";", parse_dates=["Date"])
    
There is a correlation between the two variables (R = 0.6), though recent years have gotten more chaotic.

## Sources

The prices of electricity are from <a href="https://www.omie.es/es/file-access-list?parents%5B0%5D=/&parents%5B1%5D=Mercado%20Diario&parents%5B2%5D=1.%20Precios&dir=Precios%20horarios%20del%20mercado%20diario%20en%20Espa%C3%B1a&realdir=marginalpdbc
">OMIE</a>. The files are in a strange separated format (.1), I wrote a python script that takes the average from a day (file), joins them together and saves the output into a CSV. 

The prices of natural gas are from <a href="https://www.mibgas.es/es/file-access">mibgas</a>. The speadsheets there are more detailed and include a lot of data, I took the "MIBGAS-ES Index [EUR/MWh]" from the "Indices" sheet. 
