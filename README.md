# INTRODUCTION OF FILES and DATA STRUCTURE
# Computing-Transpiration-Rate-Response-Curves-in-Response-to-atmospheric-Vapor-Pressure-Deficit
#This repository is created to handle large datasets from different loggers used in Transpiration Rate measurement in response to atmospheric vapor pressure deficit.

#This respository contains several different files containing R scripts to handle the datalogger files.

#First, let us understand a little about the experimental set-ups and different loggers used in recording different data types.

# Plant growth conditions 
Plants are grown in greenhouse for specified period of time (usually a month). There are three pocket sensors that records weather conditions inside the greenhouse experienced by the plants. These loggers are called "WEATHER LOGGERS" and are set to log data every 1 min.

# Experimental conditions 
After the plants attain right size, they are transferred to the growth chambers where controlled environments are imposed for nighttime transpiration rate measurements and daytime transpiration rate response curve construction in response to atmospheric vapor pressure deficit. Each of the three growth chambers has 18 individual weight loggers connected with data loggers and three weather loggers similar to ones in green house. The weight loggers are set to record the weight of pots every 1 min. 

For nighttime TR measurement, the chambers are set to zero PPFD and 20 degree C temperature and constant humidity. #However for daytime TR measurement, relative humidity is altered sequentially i.e each hour humidity is increased to a set levels. Since, achieving very high and low humidity inside the chambers is beyond the capability of chambers, we use add-ons i.e. humidifiers (4 per chamber) to increase the humidity and then one industrial dehumidifier in each chambers. These demumidifiers are set to sequentially decrease the humidity inside chambers. Each step is an hour long step i.e. the dehumidifier maintains a set level of humidity inside chambers for an hour before decreasing to another set levels of humidity. During these daytime steps, temperature is kept constant at 30 degree C and PPFD of approx. 600 umol m-2 s-1. We use the data from WEATHER LOGGERS to compute vapor pressure deficit (VPD) as follows:

     vpd <- 0.61375 * exp (17.502 * temperature/(240.97 + temperature)) * (1- relative humidity/100)

# DATA UPLOADED
Two folders named "WEATHER DATA" and "WEIGHT DATA" are uploaded. When experiments end, there are several hundreds files (each file with hundreds and thousands of rows) from both the loggers depending on the number of genotypes used, number of VPD steps imposed, number of days the experiment run, number of replicates for each genotype, number of chamber used etc.

A csv file named metadata is also uploaded, which contains all the information on which genotypes and replicates were placed on which chambers, which balances, which data loggers, and time interval of when VPD steps were imposed, and how long nighttime interval is etc.

# R-SCRIPTS
Following R- script files are uploaded to handle the datasets for calculation of VPDs, and Transpiration Rates.
1. To compute VPD values in each individual weather data files.
2. To compute transpiration rates using weight data files.
3. To extract parameters from the model employed (we are using AICc to select the best fitting model on our dataset).

The first article that came out of this platform is Tamang and Sadok 2018, https://doi.org/10.1016/j.envexpbot.2017.11.016.
