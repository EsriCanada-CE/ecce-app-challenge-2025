# Calculating User's Unique Neighbourhood Scores 
User's neighbourhood preferences were collected using a Survey123 App that is embedded within the Experience Builder app. <br> 
Using arcade expressions the unique score for each neighbourhood was calculated. This was accomplished using a suitability score formula where: <br>
- **Criteria #1** has a weight of *40%* 
- **Criteria #2** has a weight of *30%* 
- **Criteria #3** has a weight of *20%*
- All other criteria have weights of *2% each*
<br>
Resulting in the formula:
<br>
Weighted Score = 100 * (( 0.4 * First Choice Metric Rank) + (0.3 * Second Choice Metric Rank) + (0.2 * Third Choice Metric Rank) + (0.02 * N<sup>(4-8)</sup> Choice Metric Rank))

## Unique User Map 
### Top Three Ranks 
> Displays the top three choices from the user survey and their ranking values. 

```
// Ensure all rank fields are loaded correctly
Expects($feature, '*Rank');
 
// Get the ranking data from the Survey123 Layer
var surveyLayer = FeatureSetByName($map, "Survey");
var latestResponse = First(OrderBy(surveyLayer, 'CreationDate DESC'));
var rankingData = latestResponse['ranking_of_importance'];
 
// Split ranking data into a list
var ranks = Split(rankingData, ",");
 
// Map ranking choices to IDs
var ranks_id = [];
for (var i = 0; i < Count(ranks); i++) {
    var x = ranks[i];
    if (x == 'Transit_Stops') {
        Push(ranks_id, 1);
    } else if (x == 'Rental_Quality/Safety') {
        Push(ranks_id, 2);
    } else if (x == 'EV_Chargers') {
        Push(ranks_id, 3);
    } else if (x == 'Bikeway_Density_') {
        Push(ranks_id, 4);
    } else if (x == 'Parks') {
        Push(ranks_id, 5);
    } else if (x == 'Community_Gardens') {
        Push(ranks_id, 6);
    } else if (x == 'Community_Farmers_Markets') {
        Push(ranks_id, 7);
    } else if (x == 'Rental_Affordability_') {
        Push(ranks_id, 8);
    } else {
        // If the ranking is not recognized, add a default value
        Push(ranks_id, 9);
    }
}
 
// Check if at least 3 valid choices were mapped
if (Count(ranks_id) < 3) {
    return 'Invalid Rankings';
}
 
// Assign choices
var first_choice = Number(ranks_id[0]);
var second_choice = Number(ranks_id[1]);
var third_choice = Number(ranks_id[2]);
 
// Define rank fields and labels
var outFields = ['TransRank', 'CodeVRank', 'EV_Rank', 'Bike_Rank', 'ParkRank', 'GardenRank', 'MarketRank', 'PriceRank'];
var displayFields = ['Transit Stops', 'Rental Quality/Safety', 'EV Chargers', 'Bikeway Density', 'Parks', 'Community Gardens', 'Community Farmers Markets', 'Rental Affordability'];
 
// Initialize weighted score
var totalScore = 0;
 
// Weight top 3 choices
var topthreefields = [];
var attributes = {};
if (first_choice > 0 && first_choice <= Count(outFields)) {
    totalScore += $feature[outFields[first_choice - 1]] * 0.4;
    var ranktype = outFields[first_choice - 1];
    attributes[ranktype] = $feature[outFields[first_choice - 1]];
    Push(topthreefields, {
    fieldName: outFields[first_choice - 1],
    label: displayFields[first_choice - 1]
    });
}
if (second_choice > 0 && second_choice <= Count(outFields)) {
    totalScore += $feature[outFields[second_choice - 1]] * 0.3;
    var ranktype = outFields[second_choice - 1];
    attributes[ranktype] = $feature[outFields[second_choice - 1]];
    Push(topthreefields, {
    fieldName: outFields[second_choice - 1],
    label: displayFields[second_choice - 1]
    });
}
if (third_choice > 0 && third_choice <= Count(outFields)) {
    totalScore += $feature[outFields[third_choice - 1]] * 0.2;
    var ranktype = outFields[third_choice - 1];
    attributes[ranktype] = $feature[outFields[third_choice - 1]];
    Push(topthreefields, {
    fieldName: outFields[third_choice - 1],
    label: displayFields[third_choice - 1]
    });
}
 
// Weight remaining choices
for (var j = 0; j < Count(outFields); j++) {
    if (j != (first_choice - 1) && j != (second_choice - 1) && j != (third_choice - 1)) {
        totalScore += $feature[outFields[j]] * 0.02;
    }
}
 
// Return the weighted score multiplied by 10 (out of 100)
var WeightedMetricScore = totalScore * 10;
 
return {
    type: 'fields',
    title: 'Ranking of Top Three Metrics from Survey (Out of 10)',
    //description : '',
    fieldInfos: topthreefields,
    attributes : attributes 
  };
```
<br>

### Weighted Suitability Score 
> Calculates and displays weighted score in pop-up.

 ```
 // Ensure all rank fields are loaded correctly
Expects($feature, '*Rank');
 
// Get the ranking data from the Survey123 Layer
var surveyLayer = FeatureSetByName($map, "Survey");
var latestResponse = First(OrderBy(surveyLayer, 'CreationDate DESC'));
var rankingData = latestResponse['ranking_of_importance'];
 
// Split ranking data into a list
var ranks = Split(rankingData, ",");
 
// Map ranking choices to IDs
var ranks_id = [];
for (var i = 0; i < Count(ranks); i++) {
    var x = ranks[i];
    if (x == 'Transit_Stops') {
        Push(ranks_id, 1);
    } else if (x == 'Rental_Quality/Safety') {
        Push(ranks_id, 2);
    } else if (x == 'EV_Chargers') {
        Push(ranks_id, 3);
    } else if (x == 'Bikeway_Density_') {
        Push(ranks_id, 4);
    } else if (x == 'Parks') {
        Push(ranks_id, 5);
    } else if (x == 'Community_Gardens') {
        Push(ranks_id, 6);
    } else if (x == 'Community_Farmers_Markets') {
        Push(ranks_id, 7);
    } else if (x == 'Rental_Affordability_') {
        Push(ranks_id, 8);
    } else {
        // If the ranking is not recognized, add a default value
        Push(ranks_id, 9);
    }
}
 
// Assign choices
var first_choice = Number(ranks_id[0]);
var second_choice = Number(ranks_id[1]);
var third_choice = Number(ranks_id[2]);
 
// Define metric fields
var outFields = ['TransRank', 'CodeVRank', 'EV_Rank', 'Bike_Rank', 'ParkRank', 'GardenRank', 'MarketRank', 'PriceRank'];
 
// Initialize weighted score
var totalScore = 0;
 
// Weight top 3 choices
if (first_choice > 0 && first_choice <= Count(outFields)) {
    totalScore += $feature[outFields[first_choice - 1]] * 0.4;
}
if (second_choice > 0 && second_choice <= Count(outFields)) {
    totalScore += $feature[outFields[second_choice - 1]] * 0.3;
}
if (third_choice > 0 && third_choice <= Count(outFields)) {
    totalScore += $feature[outFields[third_choice - 1]] * 0.2;
}
 
// Weight remaining choices
for (var j = 0; j < Count(outFields); j++) {
    if (j != (first_choice - 1) && j != (second_choice - 1) && j != (third_choice - 1)) {
        totalScore += $feature[outFields[j]] * 0.02;
    }
}
 
// Return the rounded weighted score multiplied by 10 (out of 100)
var weightedscore = totalScore * 10;
weightedscore = Round(weightedscore, 1)
return $feature.Weighted_Metric_Score + weightedscore
```
<br> 


### All Ranks 
> Displays ranks of every metric in popup for explore page map

```
// Ensure all rank fields are loaded correctly
Expects($feature, '*Rank');
 
// Import data layer as feature set
var dataLayer = FeatureSetByName($map, "AppChallenge_DataTable");
 
// Define rank fields and labels
var outFields = ['TransRank', 'CodeVRank', 'EV_Rank', 'Bike_Rank', 'ParkRank', 'GardenRank', 'MarketRank', 'PriceRank'];
var displayFields = ['Transit Stops', 'Rental Quality/Safety', 'EV Chargers', 'Bikeway Density', 'Parks', 'Community Gardens', 'Community Farmers Markets', 'Rental Affordability'];
 
// Weight top 3 choices
var allfields = [];
var attributes = {};
var item = 0
while (item < 8) {
    var ranktype = outFields[item];
    attributes[ranktype] = $feature[outFields[item]];
    Push(allfields, {
    fieldName: outFields[item],
    label: displayFields[item]
    });
    item++;
}
 
// Return fields
return {
    type: 'fields',
    title: 'Ranking of All Metrics (Out of 10)',
    //description : '',
    fieldInfos: allfields,
    attributes : attributes
  }; 
  ```
<br>

## Symbolization of Explore Map 
### Unweighted Score 
> Symbolize based on score from all ranks 
```
// Ensure all rank fields are loaded correctly
Expects($feature, '*Rank');
 
// List of ranking fields
var rankFields = [
    $feature.TransRank,
    $feature.CodeVRank,
    $feature.EV_Rank,
    $feature.Bike_Rank,
    $feature.ParkRank,
    $feature.GardenRank,
    $feature.MarketRank,
    $feature.PriceRank
];
 
// Calculate the average rank
var total = 0;
var rankcount = 0;
 
// Loop through each value in the array
for (var i = 0; i < Count(rankFields); i++) {
    var rank = rankFields[i];
    if (IsNan(rank) == false) { // Check if the value is a number
        total += rank;
        rankcount++;
    }
}
 
// Calculate the average rank
var averageRank = total / rankcount;
averageRank *= 10;
return averageRank;
```
