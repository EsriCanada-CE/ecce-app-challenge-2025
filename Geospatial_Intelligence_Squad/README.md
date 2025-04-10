# Geospatial Intelligence Squad - VanMATCH
![logo](./images/VanMATCHlogo.png)

## Overview 
Esri Canada Centres of Excellence App Challenge 2025 - Centre of Geographic Sciences (COGS) Team Geospatial Intelligence Squad.  
*App:* VanMATCH (**M**odern **A**ffordable **T**ransit **C**onnected **H**omes)
<br>
# Team: 
- Charles Blanchard
- Sophie McGuiness
- Audreana Rossi 

## Mission Statement 
Vancouver is a city full of life and energy. It consistently ranks as one of the most expensive Canadian cities to live in, but also features a thriving skilled job market and is an appealing destination for young professionals<sup>1,2</sup>. The city features Canada’s third most expensive rental market—behind only two other cities in Metro Vancouver—but also places well in global sustainable city indexes<sup>3,4</sup>. These contradictions led us to ask a spatial question; where in the city best combines affordability and the qualities that young people moving to Vancouver may care about?

With this question in mind, we set out on our mission to empower individuals and families to make informed decisions about where to live in Vancouver by providing a dynamic, data-driven app that prioritizes what matters most to them. We believe that finding the perfect neighborhood shouldn't be a compromise but rather an opportunity to align your lifestyle, values, and budget with the ideal community.

VanMATCH simplifies the decision-making process by offering an intuitive and customizable experience that allows users to rank and weigh the importance of key metrics such as housing affordability/quality, access to public/green transit, green spaces, sustainable food sources, and safe biking routes. By tailoring neighborhood recommendations to individual preferences, we help users find communities that not only meet their financial needs but also enhance their quality of life in a sustainable way. The app’s metrics are largely guided by a few of the Sustainable Development Goals set out in the Federal sustainable development strategy. We specifically focused on Goal 2: Support a healthier and more sustainable food system, Goal 11: Improve access to affordable housing, clean air, transportation, parks, and green spaces, as well as cultural heritage in Canada, and Goal 12: Reduce waste and transition to zero-emission vehicles<sup>5,6,7</sup>.  VanMATCH supports users in their choice about where they want to live within Vancouver based on these goals.

Our app is designed to bridge the gap between affordability and lifestyle aspirations, supporting newcomers and long-term residents alike in their search for vibrant, sustainable communities. Whether you're a young professional seeking proximity to transit and cultural hubs, a growing family looking for parks and affordable housing, or simply someone who values access to local markets and green living, VanMATCH is here to guide you. At its core, VanMATCH is about choice, flexibility, and empowerment. The app allows users to effectively compare and analyze 22 neighbourhoods across the city by choosing what they prioritize. Users can rank the importance of eight metrics measuring affordability and sustainability to create a custom weighted score out of 100, revealing how much of a match a given community is for them. For those who prefer a simpler approach, the app also offers the option to skip the priority ranking and explore an unweighted score that takes all 8 metrics into account equally.

Through VanMATCH, we’re not just helping people find homes, we’re helping them find communities that resonate with their lifestyles, values, and aspirations for the future.


## Statement of Characteristics
To empower users to choose the metrics which are most important in their mission to select a neighbourhood to move into, VanMATCH presents an interactive view of sustainability and affordability metrics for 22 different neighbourhoods—defined as local planning areas—across the City of Vancouver.
VanMATCH is built around a simple Survey123, so users can rank what they prioritize in a neighbourhood. The 8 metrics available to rank in the survey are:
- Rental Quality/Safety
- EV Chargers
- Parks
- Community Gardens
- Community Farmers Markets
- Rental Affordability
- Bikeway Density
- Transit Stops

Survey123 was chosen for this functionality due to its simplicity and familiarity for users.
Once a ranking is selected for these metrics, the app generates a weighted neighbourhood score out of 100 upon selecting a polygon feature. This score is displayed in a table on the left side of the screen along with rankings out of ten for each of the top three metrics selected in the survey. This functionality is key to the user experience as it allows a high amount of customization, as well as instantly generated, clear results with just the selection of a feature.

Additionally, the app gives the option for an even simpler user experience using an explore map. When users click the ‘Explore’ button at any point, the need to submit a survey is removed and they can simply click through all the neighbourhood features to view the rank out of ten for all eight metrics on the left of the screen. 

The app is styled using an unweighted score, giving an overview of how neighbourhoods rank in all metrics at a glance. This styling remains the same between the ranked map based on the survey, and the explore map, maintaining cohesiveness between both maps available for users to view.

Lastly, with the aim of making a simple, but highly functional app it includes a few quality-of-life features in VanMATCH. One example of this is the address locator on the top right of the screen. This locator allows users to search an address in Vancouver, before zooming in on their selected location and allowing them to click the neighbourhood polygon the address is within to view its score and metrics. This functionality allows a user to easily enter an address from a rental listing, their current address, or even learn which areas they may want to check out while visiting the city. 

These features all contribute to VanMATCH’s simple, customizable interface, through which users can find communities that resonate with their lifestyles, values, and aspirations for the future.


## Limitations 
- Not all desired data layers - such as recycling programs, green energy, water consumption - were available on open data sources. These impact the comprehensiveness of the analysis. 
- The analysis was limited to 22 specific neighbourhoods in the City of Vancouver, rather than the entire Metro Vancouver area, due to data availability and time constraints.  
- Weighted scores could not be stored in the data table for further analysis due to the use of Arcade expressions, limiting the ability to perform additional comparisons and data exploration. 

## User Guide 
### Splash Page 
VanMATCH welcomes you with a splash page that outlines our mission statement, an abbreviated user guide, and offers you the opportunity to complete a survey for customized exploration and neighbourhood matching, or to simply experience the app in explore mode. 

### Survey
If you decide to complete the survey, the survey window appears which allows you to rank the neighbourhood criteria based your preference. Simply drag the criteria in the order of your preference, with the most important to you being at the top and the least important at the bottom. Make sure you click submit for your customized results and then press 'Explore'! 

### Customized Results Map 
The customized results map displays the weighted scores or compatibility of each neighbourhood to your preference ranking. Click on any of the neighbourhoods for more information including the overall compatibility  score, and the score the neighbourhood received for your top three criteria. Neighbourhoods with higher scores are dark green while those with lower scores are white.  If you decide you want to access our app's explore feature, simply click on the 'Explore' button! 

### Explore Map 
If you decide to use our explore feature, you may view a map which symbolizes the neighbourhoods based on their unweighted score. Again, neighbourhoods with higher scores are dark green while those with lower scores are white. Click on any of the neighbourhoods to explore the details about their scores in each of the criteria. 

### Rank Preferences Button 
While exploring either your custom map or the unweighted score map, click on the 'Rank Your Preferences' button to change the rank of your preferences or submit for the first time! If you change your preferences, be sure to click out of your current neighbourhood selection and click it again to get your updated score! 
<br> 


## General Workflows and Processes 
[Data Layer Normalization](./docs/DataNormalization.md) <br>
[Map Creation](./docs/DataNormalization.md)

## Software Used
This app was developed using Experience Builder, Survey123, ArcGIS Pro, and ArcGIS Online. 

## Data Sources 
### Data Used for Neighbourhood Analysis: 
| Data Name     | Data Source   |   Data Type  |   Data Link   |
| ------------- | ------------- |------------- | ------------- |
| Local Area Boundary  | City of Vancouver Open Data Portal | Polygon | [Local Area Boundary](https://opendata.vancouver.ca/explore/dataset/local-area-boundary/map/?disjunctive.name&location=12,49.24932,-123.13236) |
| Electric Vehicle Charging Stations  | City of Vancouver Open Data Portal  | Point | [Electric Vehicle Charging](https://vancouver.opendatasoft.com/explore/dataset/electric-vehicle-charging-stations/information/)  |
| Rental Code Violation  | City of Vancouver Open Data Portal  | Point | [Rental Code Violation](https://opendata.vancouver.ca/explore/dataset/rental-standards-current-issues/table/?sort=-businessoperator&dataChart=eyJxdWVyaWVzIjpbeyJjb25maWciOnsiZGF0YXNldCI6InJlbnRhbC1zdGFuZGFyZHMtY3VycmVudC1pc3N1ZXMiLCJvcHRpb25zIjp7InNvcnQiOiJzdHJlZXQifX0sImNoYXJ0cyI6W3siYWxpZ25Nb250aCI6dHJ1ZSwidHlwZSI6ImNvbHVtbiIsImZ1bmMiOiJBVkciLCJ5QXhpcyI6InRvdGFsb3V0c3RhbmRpbmciLCJzY2llbnRpZmljRGlzcGxheSI6dHJ1ZSwiY29sb3IiOiIjMDI3OUIxIn1dLCJ4QXhpcyI6Imdlb19sb2NhbF9hcmVhIiwibWF4cG9pbnRzIjo1MCwic29ydCI6IiJ9XSwidGltZXNjYWxlIjoiIiwiZGlzcGxheUxlZ2VuZCI6dHJ1ZSwiYWxpZ25Nb250aCI6dHJ1ZX0%3D) |
| Rapid Transit Stations | City of Vancouver Open Data Portal  | Point |[Rapid Transit Stations](https://opendata.vancouver.ca/explore/dataset/rapid-transit-stations/table/)|
| Regional Park Boundaries | City of Vancouver Open Data Portal | Polygon | [Regional Park Boundaries](https://open-data-portal-metrovancouver.hub.arcgis.com/datasets/2fbf1ad2936a404fa79ad8e0ae83f45c_6/explore ) |
| Community Garden  | City of Vancouver Open Data Portal  | Point | [Community Gardens](https://opendata.vancouver.ca/explore/dataset/community-food-markets-and-farmers-markets/table/) |
| Community Food and Farmer Markets  | City of Vancouver Open Data Portal  | CSV | [Community Food/Farmer Markets](https://opendata.vancouver.ca/explore/dataset/community-food-markets-and-farmers-markets/table/) |
| Transit Stops | Translink/Carsonyl | GeoJSON | [Transit Stops](https://github.com/carsonyl/translink-derived-datasets/tree/master) |
| Average Price - Primary Rental Market | Canada Mortage and Housing Corporation | CSV | [Average Rent Price](https://www03.cmhc-schl.gc.ca/hmip-pimh/en/TableMapChart/Table?TableId=1.10.1&GeographyId=2410&GeographyTypeId=3&DisplayAs=Table&GeograghyName=Vancouver)  |

### Literature: 
|Reference Number| Reference Name | Reference Source | Reference Link|
| ------------- | ------------- | ------------- | ------------- |
| 1 | Mercer’s 2024 Cost of Living City Ranking (Canada) | Mercer | [Vancouver Cost of Living](https://www.mercer.com/en-ca/about/newsroom/cost-of-living-in-canada-2024/) |
| 2 | Urban Work Index 2024 - Best City for Youth to Work in Canada | Youth Data Lab | [Urban Work Index 2024](https://youthdatalab.youthfulcities.com/en/insights/uwi2024) |
| 3 | 2025 Rental Market Trend Report | liv.rent | [Rental Market Trend Report](https://liv.rent/blog/wp-content/uploads/2025/02/2025_Canada_Rental_Market_Trend_Report_liv.rent_.pdf) |
| 4 | 2024 IESE Cities in Motion Index | IESE Business School - University of Navarra | [IESE Cities in Motion Index](https://www.iese.edu/media/research/pdfs/ST-0649-E) |
| 5 | Canada's Sustainable Development Strategy - Goal 2 | Government of Canada | [Goal 2](https://www.canada.ca/en/environment-climate-change/services/climate-change/federal-sustainable-development-strategy/goals/zero-hunger.html) |
| 6 | Canada's Sustainable Development Strategy - Goal 11 | Government of Canada | [Goal 11](https://www.canada.ca/en/environment-climate-change/services/climate-change/federal-sustainable-development-strategy/goals/sustainable-cities-communities.html) |
| 7 | Canada's Sustainable Development Strategy - Goal 12 | Government of Canada | [Goal 12](https://www.canada.ca/en/environment-climate-change/services/climate-change/federal-sustainable-development-strategy/goals/responsible-consumption-production.html) |

## Video: 

### Youtube Description:
VanMATCH is an app that matches you with a neighbourhood in Vancouver based on your individual affordability and sustainability preferences. 

Stock Photo Credit: iStockPhoto - heyengel https://www.istockphoto.com/photo/beautiful-aerial-view-of-downtown-vancouver-skyline-british-columbia-canada-at-sunset-gm1453719077-489580713?utm_campaign=srp_photos_top&utm_content=https%3A%2F%2Funsplash.com%2Fs%2Fphotos%2FVancouver&utm_medium=affiliate&utm_source=unsplash&utm_term=Vancouver%3A%3Avideo-affiliates%3Acontrol

Courtesy of Team Geospatial Intelligence Squad - 2025 ECCE App Challenge

| Data Name     | Data Source   |   Data Type  |   Data Link   |
| ------------- | ------------- |------------- | ------------- |
| Opening Photo | iStockPhoto - heyengel |Image | [Vancouver Image](https://www.istockphoto.com/photo/beautiful-aerial-view-of-downtown-vancouver-skyline-british-columbia-canada-at-sunset-gm1453719077-489580713?utm_campaign=srp_photos_top&utm_content=https%3A%2F%2Funsplash.com%2Fs%2Fphotos%2FVancouver&utm_medium=affiliate&utm_source=unsplash&utm_term=Vancouver%3A%3Avideo-affiliates%3Acontrol) |




