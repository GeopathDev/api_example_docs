## Use Case: Bulk request to get inventory and measures information

#### Many users want to be able to get a dataset to use within their own systems. This can be accomplished by using the ```inventory/search``` endpoint. By Omitting many of the available search parameters, the call will return all "Published Measured" inventory available.Due to the fact that no segment or target market is supplied, the measures will default to 0+ Global Impressions. Since the max return of the search endpoint is 1000 spots, the call will have to repeated using different pages.

###### Call: _This first call sets no search parameters to return all inventory. The page size is set to the maximum to increase call use efficiency_
```json
{
"page_size":1000
}
```
###### Response: _The response includes complete inventory objects for each spot. Below, the content under "inventory_items" has been omitted for space._
```json
{
    "inventory_summary": {
        "inventory_count": 1000,
        "invalid_ids": null,
        "filtered_invalid_ids": null,
        "inventory_items": [        
        
          ],
         "pagination": {
             "page": 1,
             "page_size": 1000,
             "number_of_pages": 516,
             "number_of_frames": 426237,
             "number_of_spots": 515802
         }
    }
}
```
###### Call: _Since the first response shows 516 pages for 515,802 spots, 515 more calls are required to receive the full dataset for the 0+ Global Market impressions. The second call would be:_
```json
{
"page": 2,
"page_size":1000
}
```
###### Response: _The response is the same, but with a new page of data.the content under "inventory_items" has been omitted for space._
```json
{
    "inventory_summary": {
        "inventory_count": 1000,
        "invalid_ids": null,
        "filtered_invalid_ids": null,
        "inventory_items": [        
        
          ],
         "pagination": {
             "page": 2,
             "page_size": 1000,
             "number_of_pages": 516,
             "number_of_frames": 426237,
             "number_of_spots": 515802
         }
    }
}
```

#### This can be done multiple times for different audience / market combinations by adding additional search parameters. The measures object of the inventory includes impressions and population information for global and target audiences and markets as well as reach, effective reach, and effective frequency.
```json
"spot_id": 30974557,
"measures": {
                            "measures_type": "Measures",
                            "period_days": 7,
                            "base_segment": "2032",
                            "target_segment": "2032",
                            "target_geo": "Defaulted to GLOBAL",
                            "market": "Defaulted to GLOBAL",
                            "index_comp_target": 100.0,
                            "pct_comp_pop_target_inmkt": 1.0,
                            "pct_comp_imp_target": 1.0,
                            "pct_comp_imp_target_inmkt": 1.0,
                            "freq_avg": 4.118871112,
                            "imp_target_inmkt": 468261.93666358,
                            "imp_target": 468261.93666358,
                            "imp_inmkt": 468261.93666358,
                            "imp": 468261.93666358,
                            "pct_imp_inmkt": 1.0,
                            "pct_imp_target_inmkt": 1.0,
                            "pop_inmkt": 329236175,
                            "pop_target_inmkt": 329236175,
                            "reach_pct": 0.03453051911,
                            "reach_net": 113687,
                            "trp": 0.1422267576,
                            "eff_freq_min": 3,
                            "eff_freq_avg": 5.343294496,
                            "eff_reach_net": 87635,
                            "eff_reach_pct": 0.02661780251
                        }
```
###### Call: 
_Adding the parameter period_days to the call will adjust the measures accordingly_
```json
{
"page": 1,
"page_size":1000,
"period_days":14
}
```
###### Response: 
_This is the measures object for the same spot after changing the period_days from the default of 7 to 14_
```json
"measures": {
                            "measures_type": "Measures",
                            "period_days": 14,
                            "base_segment": "2032",
                            "target_segment": "2032",
                            "target_geo": "Defaulted to GLOBAL",
                            "market": "Defaulted to GLOBAL",
                            "index_comp_target": 100.0,
                            "pct_comp_pop_target_inmkt": 1.0,
                            "pct_comp_imp_target": 1.0,
                            "pct_comp_imp_target_inmkt": 1.0,
                            "freq_avg": 5.455489196,
                            "imp_target_inmkt": 936523.87332716,
                            "imp_target": 936523.87332716,
                            "imp_inmkt": 936523.87332716,
                            "imp": 936523.87332716,
                            "pct_imp_inmkt": 1.0,
                            "pct_imp_target_inmkt": 1.0,
                            "pop_inmkt": 329236175,
                            "pop_target_inmkt": 329236175,
                            "reach_pct": 0.05214078977,
                            "reach_net": 171666,
                            "trp": 0.2844535153,
                            "eff_freq_min": 3,
                            "eff_freq_avg": 6.073469655,
                            "eff_reach_net": 154199,
                            "eff_reach_pct": 0.04683542216
                        }
```
