### Use Case: Get the top markets for a spot or multiple spots.

As seen in the Geopath Insights Suite, it's possible to find the highest indexing market for a piece of inventory. This can help our members identify new business opportunities and can be accessed by the Geopath API. 

##### In both endpoints the markets are limited to DMA or ZIP. There are also extremely long tails of data that detail tiny percentages of audience that come from distant markets. Please keep these outliers in mind as you request data and analyze the response.

##### For a single spot:

###### Call:
_This GET call is for the top zip codes for the specific spot id. The page size is limited to the top 100 on the first page._
```
https://api.geopath.org/v2.1/inventory/measures/homes/30970663?reporting_level=ZIP&page_size=100
```
###### Response:
_The response includes a pagination object detailing home many markets were returned. Additional pages can be requested. The object also includes the date the market and percentage was derived, which corresponds to the most recent impression calculation date. This response has been truncated for space_
```json
{
    "spot_id": 30970663,
    "reporting_level": "ZIP",
    "pagination": {
        "page": 1,
        "page_size": 100,
        "number_of_pages": 12,
        "number_of_homes": 100,
        "total_number_of_homes": 1195
    },
    "homes": [
        {
            "market_id": "ZIP14209",
            "homes_pct": 0.049829964,
            "dtm_calculated": "2020-04-13 09:53:02.366 -0400"
        },
        {
            "market_id": "ZIP14222",
            "homes_pct": 0.030608576,
            "dtm_calculated": "2020-04-13 09:53:02.366 -0400"
        },
        {
            "market_id": "ZIP14216",
            "homes_pct": 0.028820822,
            "dtm_calculated": "2020-04-13 09:53:02.366 -0400"
        },
        {
            "market_id": "ZIP14215",
            "homes_pct": 0.027580857,
            "dtm_calculated": "2020-04-13 09:53:02.366 -0400"
        },
        {
            "market_id": "ZIP14217",
            "homes_pct": 0.024441054,
            "dtm_calculated": "2020-04-13 09:53:02.366 -0400"
        },
          etc...
    ]
}
```
##### For a list of spots using the ```https://api.geopath.org/v2.1/inventory/measures/homes/spots``` endpoint
###### Call:
_This POST call is for the top DMAs for a list of spots . The page size is limited to the top 100 on the first page._
```json
{
    "id_list": [
        "30970663",
        "30970678"
    ],
    "reporting_level": "DMA"
}
```
###### Response:
_The response includes each spot as an object. The data per spot is identical to the GET endpoint. The objects list all the homes for a single spot before proceeding to the next spot, so be sure to check all the pages returned to ensure all data is received._
```json
{
    "homes_measures": [
        {
            "spot_id": 30970663,
            "reporting_level": "DMA",
            "homes": [
                {
                    "market_id": "DMA514",
                    "homes_pct": 0.9779435,
                    "dtm_calculated": "2020-04-13 09:53:02.366 -0400"
                },
                etc...
            ]
        },
        {
            "spot_id": 30970678,
            "reporting_level": "DMA",
            "homes": [
                {
                    "market_id": "DMA514",
                    "homes_pct": 0.9779435,
                    "dtm_calculated": "2020-04-13 09:53:02.366 -0400"
                }
                etc..
            ]
        }
    ],
    "pagination": {
        "page": 1,
        "page_size": 1000,
        "number_of_pages": 1,
        "number_of_homes": 250,
        "total_number_of_homes": 250
    }
}

```