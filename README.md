# PcpnWrnUS
Precipitation forecasts and some neural network plots for the western United States.

Quantitative precipitation forecasts from the National Weather Service's Global Ensemble Forecast System (GEFS) model are being collected and 
then passed through a Self_organizing Map (SOM) algorithm to depict the spread of the ensemble members among the phase-space domain of the 
ensemble domain.  Data is collected at 0.5 degree by 0.5 degree resolution across the western half of the United States.  This 53-by-59 domain
includes a little more that 3100 points.  The SOM algorithm uses a smallest sum of differences squared search of a collection of domains for 
the most similar pattern.  Then the algorithm makes scaled adjustments to the neighboring domains.  In this way, the algorithm is defining 
over 3100 unique precipitation patterns that cover the western half of the United States.  The GEFS model has 31 members and is run out
to 384 hours (about 15 days) four times a day.  For this project, data is only being collected twice a day (00z and 12z model runs), out to 120 hours. 
Each model run that is collected adds nearly 600 patterns to the SOM training dataset. The neural network of precipitation patterns will need at least a 
year of data to be reliably defined, but along the way the network can be used to perform various analyses of ensemble member dispersions.  Data collection 
began in mid-November 2020 and will continue going forward.  

On this page, ensemble member forecasts are collected and then processed by the latest iteration of the SOM neural network.  Each of the 31 members at each 
forecast period is assigned to its nearest neural network node, and these assignments are then tallied.  The tally of ensemble members is shown in the 
Phase-Space Plot.  The node that had the most ensemble members assigned to it is referred to as the Dominant Node, and a plot of that nodes precipitation
pattern is displayed in the middle column.  The right-hand column shows a plot of one of the ensemble members that was part of the dominant node.  This is 
meant to show that individual members are similar to the plot of the neural network node.  

Returning to the Phase-Space Plot, the assumption is that nodes around the dominant node will have similar precipitation patterns, with slight variaition 
in amounts or spatial location.  The farther an ensemble is located from the dominant node, the less similarity it will have to the members that are part of 
the dominant node.  Therefore it is possible that outlying ensemble members could be considered outliers in the ensemble domain, and should possibly not
be considered as forecasts that are likely to occur.  This sort of information may be useful in helping to reduce the spread of solutions within an 
ensemble domain. Further study of this concept is needed.  Another branch of this project will take a more detailed look at how different member forecasts
relate to their assignment within the neural network phase-space plot. 

Data for this project is being collected from the NWS Environmental Modeling Center's NOMADS server.  Python scripts are being used for data processing and 
generating images.  Information presented on these pages should not be considered official weather forecasts, and weather impact decisions should not be 
made based on this information.  Refer to local National Weather Service data outlets for official forecasts and products. 
