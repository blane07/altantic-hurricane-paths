# Hurricane Energy & Landfall [![MIT license](http://img.shields.io/badge/license-MIT-brightgreen.svg)](http://opensource.org/licenses/MIT)

❏ Accurately predict the impact areas of hurricane producing storms

❏ Forecast hurricane season energy

![Hurricane forecasting gif](https://github.com/blane07/altantic-hurricane-paths/blob/master/images/giphy.gif)

(Landfall prediction model with Hurricane Irma data)

### Background
Hurricanes   hit   the   United   States   of   America.   They   cause   death   and   destruction.   In   2017,  the   United   States   experienced   a   destructive   hurricane   season   with   485   to   1,500   killed   and  over   $280   billion   in   total   damage.   2017   is   the   costliest   hurricane   season   on   record.   How  can   we   better   prepare   for   hurricanes?   While   several   options   exist,   this   report   focuses   on  predicting   where   a   hurricane   producing   storm   may   impact   the   United   States.   This   will  provide early warning, enabling more preparation time for evacuation. 
 
The   predictive   model   uses   the   Hurdat2   (HURricane   DATabase   2)   dataset   published   by   the  National   Hurricane   Center   (NHC).   This   dataset   includes   the   best   tracks   of   storms   that  produced   hurricanes   in   the   North   Atlantic   Basin,   maximum   wind   speed,   date,   time,   and  storm status, from 1851 to 2016. 

### Data
![Paths](https://github.com/blane07/altantic-hurricane-paths/blob/master/images/paths.png)
The raw Hurdat2 dataset recorded the following information on hurricane producing storms from 1851 to 2016: 
* Storm’s first row 
  * Cyclone Number 
  * Name (cyclone’s were not formally named before 1950) 
* Date 
  * YYYYMMDD (Y: year, M: month, D: day) 
* Time (UTC) 
  * HHMM (H: hour, M: minute) 
* Record identifier 
  * C - closest approach to a coast, not followed by a landfall 
  * G - genesis 
  * I - intensity peak in terms of both pressure and wind 
  * L - landfall (center of system crossing a coastline) 
  * P - minimum in central pressure 
  * R - more detail on the intensity of the cyclone during rapid changes 
  * S - change of status of the system 
  * T - provides additional detail on the track (position) of the cyclone 
  * W - maximum sustained wind speed 
* Status of system 
  * TD - tropical cyclone of tropical depression intensity (< 34 knots) 
  * TS - tropical cyclone of tropical storm intensity (34-63 knots) 
  * HU - tropical cyclone of hurricane intensity (> 64 knots) 
  * EX - extratropical cyclone (of any intensity) 
  * SD - subtropical cyclone of subtropical depression intensity (< 34 knots) 
  * SS - subtropical cyclone of subtropical storm intensity (> 34 knots) 
  * LO - low that is neither a tropical cyclone, a subtropical cyclone, nor an extratropical cyclone (of any intensity) 
  * WV - tropical wave (of any intensity) 
  * DB - disturbance (of any intensity)  
* Latitude 
* Longitude 
* Maximum sustained wind (in knots)  
* The ‘-999’ columns contain information that was not available during that time time period 

### Approach
![Impact areas](https://github.com/blane07/altantic-hurricane-paths/blob/master/images/USA_zones.png)

We divided the East Coast into different impact areas. A model (random forest classifier) was created for each impact area.

### Results
With accuracy, the models performed at or barely above baseline. However, due to the imbalanced classes (hurricanes strike an area about 10% of the time), the F1 scored was used to evaluate the models with results ranging from 33% to 55%.

### Next Season
Looking at previous years, we were able to forecast next year's hurricane energy with an R squared value of 50.2%
![Energy](https://github.com/blane07/altantic-hurricane-paths/blob/master/images/time_series.png)

