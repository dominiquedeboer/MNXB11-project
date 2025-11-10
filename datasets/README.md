The meteorological data used in this project has been downloaded from 
the official "SMHI - Sveriges meteorologiska och hydrologiska institut"
website, <https://www.smhi.se>  

This folder contains a tarball `datasets.tgz` with SHMI open data datasets.

To extract the files, run

```console
tar zxvf datasets.tgz
```
Upon extracting all the files from datasets.tgz, only smhi-opendata_1_53430_20231007_155558_Lund.csv was left in the datasets subdirectory, other datasets were again deleted.  

The temperature data files were downloaded at the page:
<https://www.smhi.se/data/meteorologi/ladda-ner-meteorologiska-observationer/#param=airtemperatureInstant,stations=core>  
They represent the _air temperature_ collected by a given station, excluding 
the last three months at the time these datasets where downloaded.  

Also downloaded dataset smhi-opendata_5_53430_20251023_141246_rain_Lund.csv ,containing rain amount in Lund, from:
<https://www.smhi.se/data/hitta-data-for-en-plats/ladda-ner-vaderobservationer/precipitation24HourSum/53430>  
The rain dataset represents the amount of rainfall collected by given station, up until the year 2025. It counts snow the same as rain, i.e. all of the snowfall was melted and counted towards the total amount of rain fallen that day.

The filenames are the same as the original from SMHI but the temperature filename has been suffixed with `_Lund`, and the rainfall filename has been suffixed with `_rain_Lund`. 

The content of the files has been left untouched.

The use of this data is covered by the statements at this link:
<https://www.smhi.se/data/oppna-data/information-om-oppna-data/villkor-for-anvandning-1.30622>


HANDLING THE DATASETS:  
The files `smhi-opendata_1_53430_20231007_155558_Lund.csv`and `smhi-opendata_5_53430_20251023_141246_rain_Lund.csv` were preprocessed: the code doing this can be found in preprocessing.py . To execute the preprocessing, run in the terminal:
```bash
python -m pip install pandas
datasets/preprocessing.py
```
This python code produces two files we then worked with, those files being lund_cleaned.txt and lund_cleaned_rain.txt.