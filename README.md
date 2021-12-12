# Enhanced API Search for Magento 2
This module introduces a new way to search in Magento 2 API. Rather than using a querystring, use the body with the JSON format.

![Magento 2 Coding Standard](https://github.com/magedin/magento2-module-enhanced-api-search/workflows/Magento%202%20Coding%20Standard/badge.svg)

A typical search in Magento 2 API is done like below:

```bash
curl -X GET https://my-magento2.com/rest/V1/orders/?searchCriteria[currentPage]=1&searchCriteria[filterGroups][0][filters][0][field]=increment_id&searchCriteria[filterGroups][0][filters][0][value]=610001259&searchCriteria[filterGroups][0][filters][0][conditionType]=eq
```

With this module the URL is very simplified:

```bash
https://my-magento2.com/rest/V1/orders/
```

With the following body parameters:

```json
{
    "searchCriteria": {
        "pageSize": 20,
        "currentPage": 1,
        "filterGroups": [
            {
                "filters": [
                    {
                        "conditionType": "eq",
                        "field": "increment_id",
                        "value": "000000002"
                    }
                ]
            }
        ]
    }
}
```

Simple, right?

by MagedIn
