# Data Normalization (ArcGIS Pro) 

## 1. Data Preparation 
The data used for analysis was downloaded from the respective sources and uploaded into ArcGIS Pro. The majority of the data layers were ready to use for analysis, though some required initial preparation. 
<br> 
### a) Calculating Bikeway Density 
To determine the neighbourhoof score for bikeways, the density for each neighbourhood was calculated. This value was used to determine the final neighbourhood rank: 
<img src="https://github.com/rossiaudreana/GeospatialIntelligenceSquad/blob/main/images/bikewaydensity.png" alt="Bikeway Density ModelBuilder" width="100%">

### b) Transit Layer 
The transit layer found on GitHub was converted from a JSON to features in ArcGIS Pro using the JSON to Features tool. 
To reflect the greater benefits of rapid transit stops compared to other transit options, they were assigned a higher weight by doubling their values in the analysis. 

### c) Farmers Markets 
The farmer's market data set had some observations with missing addresses. These addresses were manually entered to ensure accurate geocoding and analysis. Following this step, duplicate entries were deleted and a merged address field was calculated to combine the street number, street direction, street name, street type and “Vancouver, BC”. The Geocode Assresses tool was used in ArcGIS Pro with the MergedAddress field and a single line input field. 

## 2. Ranking of Neighbourhoods 
To rank the each neighbourhood using each criteria first, the count of points, area and density were calculated for each neighbourhood. 
<img src="https://github.com/rossiaudreana/GeospatialIntelligenceSquad/blob/main/images/summarizewithin.png" alt="Normalization ModelBuilder" width="100%">
<br> 
A rank was given to each neighbourhood based on ArcGIS Pro's natural breaks (jenks) data classification method. This method accounts for non-uniform distributions, and groups similar values together - maximizing the differences between each class. 
When applicable, 10 classes were used so the rank for each neighbourhood was from 1 - 10. When less than 10 values were present in the data set 5 classes were used, where the first class took a value of 1 and the fifth class a value of 9. 
Python code was utilized within the Calculate Field tool to determine each neighbourhood's score for each criteria. 

> Example python code [using the Bikeway layer]:
```
def ranking(density): 
    if density <= 13.83: 
        return 1
    elif density < 15.45: 
        return 2
    elif density < 16.73: 
        return 3
    elif density < 17.16: 
        return 4
    elif density < 19.42: 
        return 5
    elif density < 21.55: 
        return 6
    elif density < 22.68: 
        return 7
    elif density < 28.83: 
        return 8
    elif density < 40.52: 
        return 9
    elif density <= 50.15: 
        return 10
```
> where BikewaysRank Field = ranking(!RoadDensityKM!) 

