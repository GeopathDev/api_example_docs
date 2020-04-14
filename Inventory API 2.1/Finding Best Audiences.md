## Use Case: Finding the best segments for inventory

As seen in the Geopath Insights Suite, it's possible to find the highest indexing segment for a piece of inventory. This can help our members identify new business opportunities and can be accessed by the Geopath API.

##### Using the ```https://api.geopath.org/v2.1/inventory/measures/summary/segments``` endpoint its possible to search for a single id or list of multiple ids. If no inventory details are provided, the endpoint will generate the summary based on all inventory that match the search parameters. The available search parameters are the same as in the inventory search endpoint. If specific segments are not provided, the endpoint defaults to the list of Claritas PRIZM Segments.

######Call:
_This call specifies just a single spot id and a sort order. Since no specific segments are listed to rank, it will rank the PRIZM segments._
```json
{
    "id_list": [
        "30970663"
    ],
    "sort": {
        "measure": "index_comp_target",
        "type": "DESC"
    }
}
```
######Response: _The response first details the segment ids that are included, and then breaks down the summary statistics for each segment for the inventory that matches the search parameters in the call._
```json
{
    "segment_list": [
        "1956",
        "1943",
        "1932",
        "1930",
        "1934",
        "1938",
        "1916",
        "1911",
        "1903",
        "1918",
        "1942",
        "1924",
        "1928",
        "1919",
        "1908",
        "1913",
        "1920",
        "1952",
        "1960",
        "1959",
        "1910",
        "1950",
        "1921",
        "1896",
        "1958",
        "1905",
        "1907",
        "1931",
        "1939",
        "1915",
        "1906",
        "1899",
        "1941",
        "1894",
        "1957",
        "1904",
        "1936",
        "1944",
        "1929",
        "1909",
        "1933",
        "1955",
        "1900",
        "1922",
        "1949",
        "1945",
        "1902",
        "1901",
        "1925",
        "1953",
        "1937",
        "1912",
        "1926",
        "1917",
        "1951",
        "1954",
        "1897",
        "1927",
        "1948",
        "1895",
        "1898",
        "1893",
        "1923",
        "1914",
        "1935",
        "1947",
        "1940",
        "1946"
    ],
    "segment_summaries": [
        {
            "measures_type": "segment_measures",
            "period_days": 7,
            "base_segment": "2032",
            "target_segment": "1956",
            "target_geo": "Defaulted to GLOBAL",
            "market": "Defaulted to GLOBAL",
            "index_comp_target": 1873.743977531,
            "pct_comp_pop_target_inmkt": 0.004271,
            "pct_comp_imp_target": 0.08002760528,
            "pct_comp_imp_target_inmkt": 0.08002760528,
            "freq_avg": 6.152557087,
            "imp_target_inmkt": 57648.853075908,
            "imp_target": 57648.853075908,
            "imp_inmkt": 720362.09098032,
            "imp": 720362.09098032,
            "pct_imp_inmkt": 1,
            "pct_imp_target_inmkt": 1,
            "pop_inmkt": 329236175,
            "pop_target_inmkt": 1406202,
            "reach_pct": 0.6663268414,
            "reach_net": 9370,
            "trp": 4.09961393,
            "eff_freq_min": 3,
            "eff_freq_avg": 8.100622399,
            "eff_reach_net": 7117,
            "eff_reach_pct": 0.5060862892,
            "segment": {
                "id": 1956,
                "id_ads": null,
                "id_v1": null,
                "available_search": true,
                "available_calc": false,
                "name": "40 Aspiring A-Listers",
                "description": "40 Aspiring A-Listers",
                "source_id": 1,
                "source_name": "Claritas",
                "version": "2018",
                "category_id": 2,
                "category_name": "PRIZMPremier",
                "subcategory_id": 20,
                "subcategory_name": "Young Achievers"
            },
            "frames": 1,
            "spots": 6
        },
        {
            "measures_type": "segment_measures",
            "period_days": 7,
            "base_segment": "2032",
            "target_segment": "1943",
            "target_geo": "Defaulted to GLOBAL",
            "market": "Defaulted to GLOBAL",
            "index_comp_target": 1285.2460011,
            "pct_comp_pop_target_inmkt": 0.007927,
            "pct_comp_imp_target": 0.1018814505,
            "pct_comp_imp_target_inmkt": 0.1018814505,
            "freq_avg": 5.79632373,
            "imp_target_inmkt": 73391.534719476,
            "imp_target": 73391.534719476,
            "imp_inmkt": 720362.09098032,
            "imp": 720362.09098032,
            "pct_imp_inmkt": 1,
            "pct_imp_target_inmkt": 1,
            "pop_inmkt": 329236175,
            "pop_target_inmkt": 2609768,
            "reach_pct": 0.4851672024,
            "reach_net": 12662,
            "trp": 2.812186168,
            "eff_freq_min": 3,
            "eff_freq_avg": 7.550617428,
            "eff_reach_net": 9720,
            "eff_reach_pct": 0.3724445312,
            "segment": {
                "id": 1943,
                "id_ads": null,
                "id_v1": null,
                "available_search": true,
                "available_calc": false,
                "name": "45 Urban Modern Mix",
                "description": "45 Urban Modern Mix",
                "source_id": 1,
                "source_name": "Claritas",
                "version": "2018",
                "category_id": 2,
                "category_name": "PRIZMPremier",
                "subcategory_id": 17,
                "subcategory_name": "Sustaining Families"
            },
            "frames": 1,
            "spots": 6
        },
        {
            "measures_type": "segment_measures",
            "period_days": 7,
            "base_segment": "2032",
            "target_segment": "1932",
            "target_geo": "Defaulted to GLOBAL",
            "market": "Defaulted to GLOBAL",
            "index_comp_target": 725.727706332,
            "pct_comp_pop_target_inmkt": 0.005867,
            "pct_comp_imp_target": 0.04257844453,
            "pct_comp_imp_target_inmkt": 0.04257844453,
            "freq_avg": 5.581246388,
            "imp_target_inmkt": 30671.897332686,
            "imp_target": 30671.897332686,
            "imp_inmkt": 720362.09098032,
            "imp": 720362.09098032,
            "pct_imp_inmkt": 1,
            "pct_imp_target_inmkt": 1,
            "pop_inmkt": 329236175,
            "pop_target_inmkt": 1931771,
            "reach_pct": 0.2844813528,
            "reach_net": 5496,
            "trp": 1.587760523,
            "eff_freq_min": 3,
            "eff_freq_avg": 7.468115648,
            "eff_reach_net": 4107,
            "eff_reach_pct": 0.2126052405,
            "segment": {
                "id": 1932,
                "id_ads": null,
                "id_v1": null,
                "available_search": true,
                "available_calc": false,
                "name": "31 Connected Bohemians",
                "description": "31 Connected Bohemians",
                "source_id": 1,
                "source_name": "Claritas",
                "version": "2018",
                "category_id": 2,
                "category_name": "PRIZMPremier",
                "subcategory_id": 15,
                "subcategory_name": "Midlife Success"
            },
            "frames": 1,
            "spots": 6
        },
        etc...
    ],
    "pagination": {
        "page": 1,
        "page_size": 1000,
        "number_of_pages": 1,
        "number_of_summaries": 68
    }
}
```
##### You can find more segments to search using the segment reference endpoint and provide those in the search parameters of the call. 