# Covid-19 Api
Get up to date COVID-19 data in json format. <br><br>

## Usage:

### Get all data
https://covid190api.herokuapp.com/api/data

### Filter parameters
<div>https://covid190api.herokuapp.com/api/data?{parameters}</div>

Parameter | Type | Description
------------ | ------------- | -------------
name | String | Search by a country or territory name (supports only one name at a time).
region | String | Defined regions: <ul><li>Western Pacific Region</li><li>European Region</li><li>SouthEast Asia Region</li><li>Eastern Mediterranean Region</li><li>Region of the Americas</li><li>African Region</li></ul>
territory | Boolean | Limit search to only countries or territories.<br>(true - territories only, false - countries only)
reportDate | String | Get data for a single day<br>(format: YYYY-MM-DD)
reportNumber | Integer | Similar to reportDate, each report has a report number attached.
cases | Integer | Limit search to *n* number of total confirmed cases and above.
newCases | Integer | Limit search to *n* number of new confirmed cases (since the previous report) and above.
deaths | Integer | Limit search to *n* number of total confirmed deaths and above.
newDeaths | Integer |  Limit search to *n* number of new confirmed deaths (since the previous report) and above.
transmissionType | Integer | Search by a specific type of transmission (as defined by WHO). * <ul><li>0 = Community transmission</li><li>1 = Local transmission</li><li>2 = Imported cases only</li><li>3 = Under investigation</li><li>4 = Interrupted transmission</li></ul>

0. **Community transmission** is evidenced by the inability to relate confirmed cases through chains of transmission for a large number of cases, or by increasing positive tests through sentinel samples (routine systematic testing of respiratory samples from established laboratories).
1. **Local transmission** indicates locations where the source of infection is within the reporting location.
2. **Imported cases only** indicates locations where all cases have been acquired outside the location of reporting.
3. **Under investigation** indicates locations where type of transmission has not been determined for any cases.
4. **Interrupted transmission** indicates locations where interruption of transmission has been demonstrated.
#### Response example
http://covid190api.herokuapp.com/api/data?region=European%20Region&cases=35000&reportDate=2020-03-25
```javascript
[
  {
    "name":"Italy",
    "cases":69176,
    "newCases":5249,
    "deaths":6820,
    "newDeaths":743,
    "transmissionType":1,
    "daysSinceLastCase":0,
    "region":"European Region",
    "territory":false,
    "reportDate":"2020-03-25T00:00:00.000Z",
    "reportNumber":65
  },
  {
    "name":"Spain",
    "cases":39673,
    "newCases":6584,
    "deaths":2696,
    "newDeaths":514,
    "transmissionType":1,
    "daysSinceLastCase":0,
    "region":"European Region",
    "territory":false,
    "reportDate":"2020-03-25T00:00:00.000Z",
    "reportNumber":65
    }
  ]
```
<br>*data aquired from [The World Health Organization](https://www.who.int/).* 
<br><br>Keywords: Coronavirus, COVID-19, API, JSON data
