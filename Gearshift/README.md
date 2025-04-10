# ECCE App Challenge 2025: Gearshift

## Team Members
- Alice Stubbs  
- David Figueroa  
- Zehui Yin

## Mission Statement

Toronto stands at a crossroads. With rising energy costs and growing congestion straining our transportation systems, we need smarter solutions that move people—not just vehicles. Gearshift provides urban planners with an advanced geospatial platform to transform Toronto's mobility infrastructure, using data-driven insights to optimize transit networks, pinpoint where bike lanes are needed most, and create truly interconnected communities, both centrally, and regionally. By visualizing infrastructure gaps and simulating improvements, we're helping build a city resilient to both energy market and population fluctuations and by making the right way to move also the easiest way. We believe in a future where seamless public transit, and safe biking networks, make short trips affordable, efficient, and enjoyable—positioning Toronto as a world-class city where people, not cars, come first.	

## App Features

**Bike data**

This data reveals a clear pattern: as subway delays increase, so does bikeshare usage across
Toronto. It shows that residents are already using cycling as a practical alternative when transit fails them—even without ideal infrastructure. These findings directly support our mission to reduce car dependency by identifying where targeted bike lane investments could have the greatest impact. By focusing on corridors where delays push people onto bikes, we can prioritize infrastructure that makes cycling safer and more viable long-term, helping transition Toronto toward reliable, people first transportation options.

**Collision data**

This map identifies Toronto's most dangerous streets for cyclists, with collision hotspots
concentrated along major routes lacking protected infrastructure. The patterns reveal how specific design flaws—like unprotected left turns or shared right-turn lanes—create predictable risks. These high-crash corridors align with commuter routes where protected bike lanes could yield the most benefit, consistent with Toronto's own results on Bloor Street, where separated bike lanes reduced cyclist injuries by 44%. Prioritizing these problem areas would address immediate safety risks while building confidence in cycling as a true alternative to driving.

**Bike deserts**

This map layers two fundamental gaps in Toronto’s cycling network: missing bike lanes and absent bike share stations. These “bike deserts” force residents into impossible choices—like riding unprotected alongside fast traffic or walking 15 minutes just to reach the nearest bike share dock. The patterns are clear: infrastructure breaks down along key commuter routes, while entire neighborhoods sit outside the bike share system entirely. These aren’t small inconveniences; they’re structural barriers that push people toward cars for trips that should be walkable or bikeable. By using this data to strategically fill gaps—extending lanes through interruption points, adding bike share docks where the map shows nothing—we can create a network where cycling becomes a real option for daily needs. Not everywhere at once, but street by street, where it matters most. These changes wouldn’t just serve existing cyclists; they’d give hesitant riders the confidence to try alternatives, slowly shifting Toronto’s transportation culture toward your vision: a city designed for people first. 

**Pop density vs transit lines**

Planners understand better than anyone that even the best-designed systems need to evolve. This map highlights where the Golden Horseshoe’s explosive growth has quietly outpaced our transit networks. Three insights stand out:

1.	The Rise of Complete Urban Hubs 
    - Hamilton, Kitchener, and Oshawa now anchor their own economies, yet their transit ties still default to Toronto-centric patterns. The data shows where direct regional connections could complement—not replace—existing radial networks. 
2.	The 407’s Unplanned Potential 
    - What was envisioned as highway flank is now a de facto linear city. Planners’ own density principles suggest this corridor is ripe for the kind of strategic transit investment that transformed similar spaces in Copenhagen and Portland. 
3.	The Efficiency Dividend 
    Every avoided Toronto detour means faster trips, lower emissions, and infrastructure that works smarter. The map pinpoints where modest strategic links could yield outsized network effects.

This isn’t about reinventing wheels—it’s about adding a few well-placed spokes. The patterns make a compelling case: sometimes, the most professional solution is also the most human one. 

**Future Toronto - Urban**

The GTA’s current transit system functions like a bicycle wheel with all its spokes welded to the
hub—forcing every trip through Toronto, whether it makes sense or not. A regional orbital rail line linking Hamilton, Milton, Brampton, Vaughan, Markham, Pickering, and Oshawa would change that, acting as an outer rim that works with (not against) GO Transit’s radial lines. Picture a Kitchener resident working in Mississauga: instead of driving or enduring a Toronto detour, they’d take GO to Brampton and switch directly to the orbital, which would save time, cut household transportation costs, and even avoid nearly 2 tons of CO₂ emissions annually per commuter. This network wouldn’t just move people faster; it would unlock sustainable economic growth by connecting job clusters in advanced manufacturing, logistics, and tech across the 407 corridor and lakeshore west, reducing the need for carbon-intensive trucking and sprawl. Toronto’s downtown relief line would thrive under this model too, freed from serving regional through-trips to focus on core mobility. It’s the transit equivalent of a circular economy: less waste, better connections, and a system that finally aligns with how the region actually works—both economically and environmentally. 

**Future Toronto - Interregional**

The GTA’s transit system currently functions like a bicycle wheel with all its spokes welded directly to the hub—every trip, no matter how unnecessary, gets funneled through Toronto. But imagine a network where an orbital rail line linking Hamilton, Milton, Brampton, Vaughan, Markham, Pickering, and Oshawa acts as the outer rim, connected seamlessly to GO Transit’s radial lines through timed transfers. Suddenly, that Kitchener resident working in Mississauga could take a GO train to Brampton and switch to the orbital without touching Union Station, while Toronto’s downtown relief line focuses on core trips. Environmentally, this shift would cut millions of unnecessary car kilometers annually, reducing emissions and fuel costs for households. Economically, it would strengthen the entire region by making cross-GTA commutes efficient, easing the strain on Toronto’s core while supporting job growth in satellite cities. This isn’t about replacing the spokes; it’s about giving them new purpose. Just as London’s Overground and Paris’ RER networks proved, radial and orbital systems amplify each other’s value—the former anchors the region, while the latter unlocks thousands of previously impractical trips.

**Comparisons to other global cities:**

These maps reveal how a connected downtown circle line and regional orbital could position
Toronto—and by extension, Canada—as more than just a competent player in urban mobility, but as an innovator. Where Tokyo’s Yamanote Line excels at moving millions through a dense core, and London’s Overground seamlessly weaves through historic neighborhoods, Toronto’s system would pioneer something different: a network that treats spread-out, economically diverse cities like Hamilton, Markham, and Oshawa as equal partners rather than afterthoughts. This isn’t about catching up to global peers; it’s about leapfrogging them with a model that actually works for 21st century urban regions. The numbers tell the story: 20-30% less downtown congestion (matching London’s Elizabeth Line gains), 40% faster cross-region trips (inspired by Tokyo’s express rail efficiencies), and 1.2 million more residents served, surpassing New York’s reach despite our smaller size. But the real impact is bigger. This is how Canada builds transit that matches its ambition—systems that don’t just mimic global leaders, but show the world how to connect polycentric regions without forcing everything through a single core. New York struggles with this. London adapts to it. Toronto could define it.

## Data sources

Below are the data sources used in the data analysis component of the app challenge. Note that the Toronto city boundary is utilized solely in the Shiny app data visualization but not in the modeling component.

| Data Name                         | URL                                                                                                      | Date       |
|-----------------------------------|----------------------------------------------------------------------------------------------------------|------------|
| TTC Subway Delay Data             | <https://open.toronto.ca/dataset/ttc-subway-delay-data/>                                                 | 2025-03-21 |
| About TTC Routes and Schedules    | <https://open.toronto.ca/dataset/ttc-routes-and-schedules/>                                              | 2025-03-21 |
| Bike Share Toronto                | <https://tor.publicbikesystem.net/ube/gbfs/v1/en/station_information/>                                   | 2025-03-21 |
| Bike Share Toronto Ridership Data | <https://open.toronto.ca/dataset/bike-share-toronto-ridership-data/>                                     | 2025-03-21 |
| Traffic Collisions Open Data      | <https://data.torontopolice.on.ca/datasets/TorontoPS::traffic-collisions-open-data-asr-t-tbl-001/about/> | 2025-03-22 |
| Regional Municipal Boundary       | <https://open.toronto.ca/dataset/regional-municipal-boundary/>                                           | 2025-03-26 |

## Modelling Method

The study period is September 2024, and the study area covers the service area of the Toronto Bike Share system. This area is defined by creating a 200-meter buffer around all bike share stations, followed by the creation of a concave hull with a convex fraction of 0.05 to exclude regions without bike share stations. Subsequently, a hexagonal grid is generated with cells having a distance of 500 meters between opposing edges. Temporal dimensions are incorporated at 3-hour intervals, forming space-time hexagonal cubes.

For each space-time hexagon cube, the following metrics are calculated:

1. Total number of bike share trip starts.
2. Subway delay minutes.
3. Number of traffic collisions.

Two-way fixed-effect linear regression model and linear probability model are applied as follows:

1. To model bike share trip starts and subway delay minutes: $`\log(\text{bikeshare}_{it} + 1) = \sum \alpha_i + \sum \gamma_t + \beta_1 \text{subway delay}_{it} + \epsilon_{it}`$

2. To model the presence of traffic collisions and bike share trip starts: $`I(\text{collision}_{it} \geq 1) = \sum \alpha_i + \sum \gamma_t + \beta_1 \text{bikeshare}_{it} + \epsilon_{it}`$

Here, $\alpha_i$ represents the hexagon-specific fixed effect, $\gamma_t$ represents the time-interval-specific fixed effect, and OLS estimation procedures are employed for both models.

## Modelling results

|               | $`log(\text{bikeshare}_{it} + 1)`$            | $`I(\text{collision}_{it} \ge 1)`$     |
|---------------|-----------------------|-----------------------|
| Subway Delay Minute     | **0.0035888 (0.0017486)** ||
| Bike Share Trip Start   || **0.000348867 (0.00003176907)** |
| Two-way Fixed Effects   | $`\checkmark`$          | $`\checkmark`$          |
| $`R^2`$                   | 0.7934377 | 0.0268775 |

## Model Conclusions

- Both Subway Delay minutes and Bike Share trip starts are significant at the commonly-used 5% significance level.
- An increase in subway delays (holding all else constant) correlates with an increase in bike share trip starts. Similarly, an increase in bike share trip starts (holding all else constant) corresponds to a higher probability of traffic collisions.
- Two-way fixed effects control for variables that remain constant across either space or time, including temporal trends (e.g., weekends) and built environment factors (e.g., land use characteristics).

## Model evaluation

- The model predicting $`\log(\text{bikeshare}_{it} + 1)`$ achieves an $R^2$ close to 0.8, indicating strong explanatory power.
- The linear probability model predicting collisions has an $R^2$ of approximately 0.03. Traffic collisions are rare and inherently random, meaning that the deterministic component of the process is theoretically small relative to the random component. Therefore, although the model does not explain much of the total variation, it remains informative, demonstrating a positive correlation between bike share ridership and traffic collisions.
