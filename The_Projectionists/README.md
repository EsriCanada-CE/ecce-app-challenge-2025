# BiTransit Canada
## By NSCC team "The Projectionists" 

BiTransit is an easy-to-use web app that visualizes the reltionship between demand for, and access to public transit in two Canadian cities by dissemination area. 


## Mission Statement
In 2021, Statistics Canada reported that 83.9% of working Canadians relied on a car for their work commute, with only 13.9% of Canadians relying on sustainable transportation methods for their commute . Road transportation emitted 118megatonens of CO2 in 2021, showing a decrease in passenger vehicle emissions since 2005 due to COVID-19 travel restrictions and increased vehicle efficiency .  The dissolution of COVID-19 regulations since 2021 has returned commuters and traffic congestion to their pre-COVID-19 numbers, subsequently increasing commute time and CO2 emissions. On average, Canadians spend $1370/month on car ownership, a price that is becoming increasingly inaccessible as other living costs (i.e. food, rent, and utilities) increase at a rate outpacing wage increases . As a result, public transit ridership has been continuously increasing after COVID-19 regulations caused significant ridership decreases . 

BiTransit Canada is an easy-to-use web application that visualizes the demand for public transit against current transit accessibility by dissemination area in the cities of Victoria, and Hamilton. This app is designed to highlight areas within these cities where investment in public transit is most needed, and where budgets would be best spent. It can also be used as a tool for current and incoming residents who rely on public transportation to identify areas in these cities with the highest public transit accessibility. 

## Suitability Index Explanation
BiTransit Canada compares two suitability layers for each city, a suitability layer for public transit demand, and a suitability layer for public transit accessibility. Higher suitability scores indicate areas with higher demand for public transit, and greater accessibility. Therefore, areas with higher demand values and lower accessibility values would benefit most from public transit investment. 

## User Guide 
Navigate to one of the three city tabs located at the top of BiTransit Canada’s homepage. Clicking on a tab displays the transit demand suitability map and the transit accessibility suitability maps are overlayed. Use the swipe tool by clicking on the vertical “swipe” bar on the map, dragging left and right to compare suitability scores of each dissemination area within your selected city. In the menu bar on the left side of the map screen, toggle "off" of the swipe function to view one suitability map at a time. 

## Methodology and Justification 
### Data Acquisition 
As stipulated, all data used in the creation of BiTransit Canada was collected from open data portals. Local feature shapefiles were collected from city open data portals and all demographic data was sourced from the Statistics Canada Census Program Data Viewer dashboard. All features were amalgamated to dissemination areas within city boundaries, which represent the smallest geographic level available through Statistics Canada. 

### Workflow 
BiTransit Canada compares two suitability layers, one for public transit demand and one for public transit access. The workflows for each suitability are broken down as follows:

#### Transit Demand Suitability Layer Workflow:

1. Six demographic indicators were selected from Statistics Canada and downloaded by city dissemination areas from the Census Program Data Viewer dashboard. These indicators include:
   - Population density (per square Km; 2021)
   - Percentage of commuters using public transit (2021)
   - Percentage of commuters using active transit (2021)
   - Average commute duration in minutes (2021)
   - Total median household income in CAD (2020)
   - Employment rate for 15 and over (2021)
2. Criteria were created to rank values of each indicator:
   - Population density: High Population Density = **High Demand; Low Population Density = Low Demand**
   - Percentage of commuters using public transit: **High Percentage = High Demand; Low Percentage Density = Low Demand**
   - Percentage of commuters using active transit: **High Percentage = Low Demand; Low Percentage Density = High Demand**
   - Average commute duration in minutes: **High Duration = High Demand; Low Duration = Low Demand**
   - Total median household income in CAD: **Low Income = High Demand; High Income = Low Demand**
   - Employment rate for 15 and over: **High Rate = High Demand; Low Rate = Low Demand**
3. These polygon feature classes were converted to raster layers with a cell size of 10 using the Polygon to Raster tool in ArcGIS Pro.
4. Raster layers were reclassified to five classes using the natural breaks classification method in order to account for data variations across cities while maintaining a consistent workflow for each city. A reclassified value of 1 = low demand, 5 = high demand.
5. All six raster layers were combined using the Raster Calculator tool in ArcGIS Pro to produce the transit demand suitability layer.
6. The transit demand suitability layer was converted back to a polygon feature layer to improve load times and functionality when publishing the map to the web page.

#### Transit Accessibility Suitability Layer Workflow:

Three accessibility indicators were derived from bus stop, bus route, dissemination area (DA), street centreline, and civic address data.
   - Bus stops per Km of transit route by DA
   - Percentage of street centreline covered by transit route by DA
   - Percentage of  civic addresses within 400m of a bus stop by DA

**Bus stops per Km of transit route**
1. Bus stops and transit routes (by length) were summarized within the DA layer using the Summarize Within tool in ArcGIS Pro
2. A new column was created in the attribute table of the resulting DA layer and was populated by dividing the sum of stops column by the total bus route length column
3. This polygon layer was converted into raster format using the Polygon to Raster tool
4. The resulting raster layer was reclassified to 5 classes using the natural breaks classication method where 1 = low accessibility and 5 = high accessibility
**Percentage of street centreline covered by transit route by DA**
1. Street centrelines were spatially joined to the DA summarize within layer and summarized (by length) within the same DA layer in ArcGIS Pro
2. A new column was created in the attribute table of the resulting DA layer and was populated by dividing the total transit route length by the total street centreline length and multiplying by 100
3. This polygon layer was converted into raster format using the Polygon to Raster tool
4. The resulting raster layer was reclassified to 5 classes using the natural breaks classication method where 1 = low accessibility and 5 = high accessibility
**Percentage of  civic addresses within 400m of a bus stop by DA**
1. Civic addresses were spatially joined to the DA layer and summarized within that DA layer to get the total number of civic addresses per DA
2. Bus stops were buffered with a 400m dissolved buffer. A distance of 400m was chosen as it correlates to 5 minutes of walking time on average, and a reasonable distance to walk to a bus stop. 
3. The civic addresses were clipped to the bus stop buffer
4. The clipped civic address layer was summarized within the DA layer to add the number of civic addresses that are located within 400m of a bus stop.
5. A new column was created in the DA layer and populated by dividing the number of buffered addresses by the number of total addresses and multiplying by 100
6. This polygon layer was converted into raster format using the Polygon to Raster tool
7. The resulting raster layer was reclassified to 5 classes using the natural breaks classication method where 1 = low accessibility and 5 = high accessibility

All three raster layers were combined using the raster calculator in ArcGIS Pro to produce the final transit accessibility suitability layer

Raster layers were converted back to polygons for faster load time within the application 

## References
  1. https://www12.statcan.gc.ca/census-recensement/index-eng.cfm?MM=1
  2. https://tc.canada.ca/en/corporate-services/transparency/corporate-management-reporting/transportation-canada-annual-reports/transportation-canada-2023/greenhouse-gas-emissions
  3. https://www.ratehub.ca/blog/what-is-the-total-cost-of-owning-a-car/
  4. https://www150.statcan.gc.ca/n1/daily-quotidien/250220/dq250220d-eng.htm


   

