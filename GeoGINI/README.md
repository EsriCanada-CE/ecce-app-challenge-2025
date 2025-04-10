Copyright © 2025 Skyler Grasley, Noyln Lakhanpal, Matthew Kastanis. 
 
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. 
Visit https://www.gnu.org/licenses/gpl-3.0 for the GNU GPL 3.0 license.

# GeoGINI
HomeInsight Web App: https://experience.arcgis.com/experience/1cc1b555590e4f1bacc2b79f5e4dfadd <br/>

## Team
- Matthew Kastanis
- Nolyn Lakhanpal
- Skyler Grasley

## Mission Statement

Affordability is a critical topic in todays economic climate. When we think of affordability, many of us would think of housing. Today the housing market is reaching unprecidented rates, because of this, people often look for solutions. This process can lead to gentrification, a process that by definition is taking away from affordable housing that is lacking in the current housing options. This causes displacement of low-income and vulnreble populations. Our mission is to inform people about gentrification and its influence on affordable housing, while providing an index through our app, HomeInsight, communicating dissemination areas in the GTA at greater risk of gentrification. Communicating a quantification of gentrification has ethical risks, to mitigate this, our goal is to provide actionables for those accessing our app, providing information about how to comminicate with local elected officials to, to policy intruments for mitigating displacement and advocating for affordable housing discussed in the app.

## Goals of the App
- Inform users and communities about the risk of gentrification in their neighbourhoods through a vulnerability index indicating high and low risk areas.
- Empower users with an interactive map of elected officials, enabling advocacy through policy change to mitigate displacement and promote affordable housing.

## Web Description and Application Features 
Gentrification Risk Explorer App:
Helps determine gentrification risk at a neighbourhood scale or smaller through a vulnerability index developed from four indicators of gentrification.

Details:
- Communities most often do not expect drastic increases in price, therefore, they are unprepared: and this can have drastic consequences.
- This app allows residents of Durham and Toronto to understand the risk their communities are at, and just how fast neighbourhoods can be gentrified, resulting in their displacement from the homes where they’ve built countless memories.
- The user starts with being notified to search for their neighbourhood through the easy to use search bar or any location of interest.
- The searched location displays the details about their neighbourhood, along with the gentrification risk level from lowest to highest risk.
- Low risk is associated with neighbourhoods that are unlikely to undergo gentrification or already have undergone renewal and revitalization.
- High risk is associated with neighbourhoods that are deteriorated, reveal a “rent gap” pattern, and generally have the characteristics of lower-income populations (i.e. Smaller population of degree holders).

Filtering by risk levels:
- By selecting the risk levels (one or multiple), users can visualize all the areas pertaining to the risk level chosen.
- With this, users can see the number of areas based on the selected risk level rise and fall through a gauge displaying the total areas at that risk level.

## Spatial Analysis and Calculations
To create the gentrification index, the following indicators for gentrification risk were used: Median Annual Household Income, Median House Value, Median Monthly Rent, and the Percentage of Persons who hold a Bachelor’s Degree or Higher. 

1. Deciding on weights 
Weighting is heavily reliant on research and expertise. Many articles such as Understanding urban gentrification through machine learning rank the importance of household income as the biggest driving factor, followed by house value and rent, and lastly education. The weightings were given to these variables via point allocation, resulting in 35%, 25%, 25%, and 15% weightings being given corresponding to each rank. 

2. Standardizing the indicators for compatibility 
Standardizing the data for compatibility required using a method that would prevent skewing of data. As a result, robust standardization was utilized as the data had plenty of outliers due to the nature of income and house value datasets. 

3.Rescale the indicators with Z-score 
Rescaling the data using Z-score was due to its ability to be somewhat robust to outliers and skewness, along with it keeping the data continuous to prevent loss of data, improving accuracy. Percentile was another option, however, when comparing the results, z-score displayed a more accurate dataset, although the similarities were nearly identical. 

4. Combine using mean 
Combining the data using mean was the best choice as the data of each indicator is likely to be spread out with sum, making it harder to predict gentrification. 

5. Classify into classes using quantile 
Classification by quantile was best as it categorizes the data while preventing misrepresentation of the data due to outliers which no matter what are present in this dataset due to the nature of the data. 

Overall, the decisions made were done to maintain accuracy for the data where we need it the most (Those highest at risk). 

## Data Sources

Toronto Dataset 
Boundary layer of Toronto neighbourhoods: https://open.toronto.ca/dataset/neighbourhoods/  
Toronto demographic data of neighbourhoods: https://open.toronto.ca/dataset/neighbourhood-profiles/  

Durham Dataset 
Durham demographic data by dissemination area via map server: https://maps.durham.ca/arcgis/rest/services/Open_Data/Durham_OpenData/MapServer 

## Reference List
Easton, S., Lees, L., Hubbard, P., & Tate, N. (2019). Measuring and mapping displacement:  

The problem of quantification in the battle against gentrification. Urban Studies, 	57(2), 286–306. https://doi.org/10.1177/0042098019851953  

Firth, C., Fuller, D., Thierry, B., & Winters, M. (2021). Gentrification, urban interventions and 

equity (GENUINE): A map-based gentrification tool for Canadian metropolitan 	areas. Statistics Canada, 32(5). https://doi.org/10.25318/82-003-x202100500002-	eng  

Ghaffari, L., Klein, J., & Angulo Baudin, W. (2017). Toward a socially acceptable  

gentrification: A review of strategies and practices against displacement. Geography 	Compass, 12(2). https://doi.org/10.1111/gec3.12355  

Government of Canada. (2025, March 27). Statistics Canada: Canada’s national statistical  

agency. Statistics Canada: Canada’s national statistical agency. 	 

https://www.statcan.gc.ca/en/start  

Reades, J., De Souza, J., & Hubbard, P. (2018). Understanding urban gentrification through  

machine learning. Urban Studies, 56(5), 922–942.  

https://doi.org/10.1177/0042098018789054  

Van Criekingen, M., & Decroly, J.-M. (2003). Revisiting the diversity of gentrification:  

Neighbourhood Renewal Processes in Brussels and Montreal. Urban Studies,  

40(12), 2451–2468. https://doi.org/10.1080/0042098032000136156 
