
# ADVISE PROJECT 

**Original PM3 developer**: Yuandong Liu 

**Original Corridor developer**: Yangsong Gu

**Edit Date**: 03/12/2022

1. PM3 report

> 1.1 LOTTR (Level of Travel Time Reliability) 

>> - Directory: /MOEs/LOTTR/
>> - Monthly/Quarterly/Yearly

> 1.2 TTTR (Truck Travel Time Reliability)

>> - Directory: /MOEs/TTTR/
>> - Monthly/Quarterly/Yearly

> 1.3 PHED (Peak Hour Excessive Delay)

>> - Directory: /MOEs/TTTR/
>> - Monthly/Quarterly/Yearly
>> - <span style="color: red">**PAY ATTENTION TO POPULATION**</span>span>, use mostly recent year's MPO population for current PHED calculation. 
>> - Population data is from Census Bureau. see [link](https://www.census.gov/programs-surveys/popest/technical-documentation/research/evaluation-estimates/2020-evaluation-estimates/2010s-totals-metro-and-micro-statistical-areas.html). Note, we are using MPO population, not other community population. 
>> - This caclaltion is also involved with speed limit. So please make sure you checked out the latest shapefile, and see if all segments have matched speed limit. Otherwise, you have to manually match speed limit for segments, using TDOT speed limit shapefile from [E-Trims](https://e-trims.tdot.tn.gov/Account/Logon?url=https%3a%2f%2fe-trims.tdot.tn.gov%2f) or Google map streetview. 

2. Corridor MOEs

There are 30 corridors of interest in the state of Tennessee. We have been monitoring the Measurement of Performance for them. 

![Corridors](advisecorridors.PNG)

All the scripts for corridor MOEs are saved under this directory: ```..\Scripts\CorridorMOEs\Scripts```.You can run for each region or parallel. 

> 2.1 LOTTR
>> - same as abovementioned

>> - same as abovementioned

> 2.3 Excessive Delay
>> - We dont apply population.

> 2.4 Travel Time relabiity 

>> - Something related to ```$85^{th}$, $95^{th}$ and $50^{th}$```travel time.
>> - Refer to NPMRDS->[help](https://npmrds.ritis.org/analytics/help/) page. 

>> 2.4.1 PTI
>> - Planning time index 

>> 2.4.2 BTI
>> - buffer time index

>> 2.4.3 TTI
>> - Travel Time Index

> 2.5 Delay Cost

- Refer to NPMRDS->[help](https://npmrds.ritis.org/analytics/help/) page. 

>> 2.5.1 Passenger Vehicle Delay 

>> 2.5.2 Commercial Verhicle Delay

>> 2.5.3 Delay Cost


3. Data Preparation

3.1 Check the MPO segments.
	
	* This is an important step as NPMRDS changes shapefile once a year. So you need to make sure your are using the latest shapefile for current year's cacluation. 
	* The shapefile-speed data-configuration file should always be consistent.
	* To check the segments, I suggest you go to ```NPMRDS--> dashboard-->add widgets for four MPOs--> display (current year) map of LOTTR for interstate/non-interstate--> export the map segments```, and use these segments to download the data. 
	
3.1 Configuration files. 

	* MPOs: ```..\Scripts\MPOCsvFileSLQ4```
	* Corridors: ```..Scripts\CorridorMOEs\corridors```
	* <span style="color:blue">Please prepare the segment geometry data as current order. Do not change the column order.</span>
	* The segment information is avaiable along with the raw data. 
	* Pay attention to the speed limit, if there are new segments, you have to match speed limit for them.

3.2 Split raw data. 
	
	* The raw dataset downloaded from NPMRDs is very big. So we have to split it into smaller dataset at segment level. 
	* Scripts: ```..\Scripts\splitlink```
	* To accelerate, you can run multiple scripts at the same time. 

3.3 Run df_class. 
	* df_class is needed when you run PHED scripts. 
	* it is a factor used to estimate peak hour AADT 
	* Directory: ```..\Scripts\MOEs\Dfclass```

4. Save your results.

	* MPOs: ```..\Dropbox\Output2\Advise Project\MPO```
	* Corridors:```..\Dropbox\Output2\Advise Project\Corridor\Summary tables Q4 2021```

4. Other suggestions

	- Read NPMRDS help documents. Only knowing how to run code would not go on for long. 
	- Pay attention to details, otherwise errors are around you. Further, :blush: pressure is around you!:wink: 
	- There might be some ArcMap operation involved. 

5. Visualization
	
	- Map visualization is always a primary option to display your results.
	- If not possible, PowerBI is a good alternative.  


	




