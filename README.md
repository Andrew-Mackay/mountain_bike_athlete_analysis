# Mountain Bike Athlete Analysis
This project explores the data behind the top level mountain bike athletes in their respective disciplines.

## Project Status: 
I have collected all the data I want to explore and, from this, calculated the average age of event winners for each discipline (DH, XCO and Enduro). 

For now I do not plan to do any further exploration on this data however I do intend to follow up at some point in the future as I have only scratched the surface of what I have collected. If you conduct your own exploration into the data I would be interested to hear about it.

## Average Age for Event Winners (years)

DH Mens: 26.53

DH Womens: 26.64

Enduro Mens: 26.83

Enduro Womens: 27.72

XCO Mens: 29.11

XCO Womens: 28.0

## Data Overview
The data has been collected from https://www.uci.org/mountain-bike/results. 

The process for data collection can be found in [data_collection.ipynb](notebooks/data_collection.ipynb). The data has been saved as json and can be found in [data/](data/). All stages of the data collection process have been stored. [competitions_with_races_and_events_and_results.json](data/competitions_with_races_and_events_and_results.json) contains the final data used in [analysis.ipynb](notebooks/analysis.ipynb).

### Restrictions:
The following restrictions have been applied when conducting this investigation however it should be trivial to modify [data_collection.ipynb](notebooks/data_collection.ipynb) to collect any additional data if you require.

The data has been collected from 2009-2020 (where available).

The chosen disciplines to analyse are downhill (DHI), cross-country olympic (XCO) and enduro. 

Data has only been collected for men and women competeing at the 'Elite' level. 

For DHI and XCO disciplines, the data has been taken from world cups and world championship competitions. For enduro the data has been collected for the enduro world series (EWS).

Qualifying events have been excluded.

<details>
<summary>Data Sample</summary>

```
{
    // Race Type ID (DH = 19, Enduro = 122, XCO = 92)
    19: {
        // 2009-2020 (where available)
        Year: [
            // Competition
            {
                "CompetitionId": 60947,
                "StartDate": "/Date(1604098800000)/",
                "EndDate": "/Date(1604185200000)/",
                "CompetitionName": "MERCEDES-BENZ UCI MTB WORLD CUP - DHI",
                "CountryName": "PORTUGAL",
                "IsInProgress": false,
                "IsDone": false,
                "CountryIsoCode3": "POR",
                "CountryIsoCode2": "PT",
                "ClassCode": "CDM",
                "FlagCode": "pt",
                "Date": "31 Oct-01 Nov 2020",
                // All races for the competition, event data has only been collected for 
                "races": [
                    // Event data has only been collected for the specified races
                    ...,
                    {
                        "Id": 165330,
                        "RaceCode": "F",
                        "Index": 6,
                        "StartDate": "/Date(1604098800000)/",
                        "EndDate": "/Date(1604098800000)/",
                        "RaceName": "Men Elite - Downhill",
                        "CategoryCode": "Men Elite",
                        "RaceTypeCode": "DHI",
                        "DisciplineCode": "MTB",
                        "StartLocation": "Lousa",
                        "EndLocation": null,
                        "MandatoryDate": "/Date(1604185200000)/",
                        "EventResultPage": [],
                        "Venue": "Lousa",
                        "Date": "31 Oct 2020",
                        "events": {
                            "Men Elite": {
                                "EventCode": "D2EV208411",
                                "EventId": 229840,
                                "RaceId": 0,
                                "IsTeamEvent": false,
                                "CompetitionId": 0,
                                "CompetitionName": null,
                                "WinnerName": "BRUNI Loic",
                                "EventName": "General Classification",
                                "RaceTypeName": null,
                                "StartLocation": null,
                                "EndLocation": null,
                                "MandatoryDate": "/Date(-62135596800000)/",
                                "EndDate": "/Date(-62135596800000)/",
                                "DisplayInfo": "01 Jan 0001",
                                "CompetitorTypeId": 1,
                                "IndividualWinner": "BRUNI Loic",
                                "UnknownIndividualWinner": null,
                                "ForExport": false,
                                "DisciplineId": 0,
                                "Page": 0,
                                "Skip": 0,
                                "PageSize": 0,
                                "Total": 0,
                                "Items": [],
                                "Filter": {
                                    "Filters": []
                                },
                                "Sort": {
                                    "Field": null,
                                    "Dir": null
                                },
                                // Ordered by position
                                "results": [
                                    {
                                        "ResultId": 6235453,
                                        "RankNumber": 1,
                                        "SortOrder": 1,
                                        "TeamType": 3,
                                        "Rank": "1",
                                        "Bib": "4",
                                        "MandatoryDate": "/Date(1604185200000)/",
                                        "BirthDate": "/Date(768780000000)/",
                                        "Age": "26",
                                        "IndividualDisplayName": "BRUNI Loic",
                                        "IndividualFirstName": null,
                                        "IndividualLastName": null,
                                        "UnknownIndividualDisplayName": null,
                                        "UnknownIndividualFirstName": null,
                                        "UnknownIndividualLastName": null,
                                        "DisplayName": "BRUNI Loic",
                                        "DisplayFirstName": null,
                                        "DisplayLastName": null,
                                        "IsoCode2": "FR",
                                        "NationName": "FRA       ",
                                        "IndividualCountryIsoCode2": "FR",
                                        "IndividualCountryName": "FRA       ",
                                        "IndividualCountryNameText": "FRANCE",
                                        "UnknownIndividualCountryIsoCode2": null,
                                        "UnknownIndividualCountryName": null,
                                        "UnknownIndividualCountryNameText": null,
                                        "TeamName": "SPECIALIZED GRAVITY",
                                        "ResultValue": "00:03:54.288",
                                        "PointPcR": 250.0,
                                        "TeamPointPcR": null,
                                        "PcRPrefix": "250",
                                        "PcRSuffix": "",
                                        "Irm": null,
                                        "FlagCode": "fr",
                                        "Gender": "",
                                        "IndividualGender": null,
                                        "UnknownIndividualGender": null,
                                        "Phase": null,
                                        "Heat": null
                                    },
                                    ...
                                ]

                        }

                ]
            },
            ...
        ],
        ...
    },
    ...
}
```
</details>


## Setup
Install the required python packages:
```
pip install -r requirements.txt
```

Start jupter notebook server:

```
jupyter notebook
```

## License
[MIT](LICENSE)