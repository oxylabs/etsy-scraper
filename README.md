# Etsy Scraper

[![Oxylabs promo code](https://user-images.githubusercontent.com/129506779/250792357-8289e25e-9c36-4dc0-a5e2-2706db797bb5.png)](https://oxylabs.go2cloud.org/aff_c?offer_id=7&aff_id=877&url_id=112)


Oxylabs’[ Etsy Scraper](https://oxy.yt/Vafh) is a data gathering solution allowing you to extract real-time information from an Etsy website effortlessly. This brief guide explains how an Etsy Scraper works and provides code examples to understand better how you can use it hassle-free.

### How it works

You can get Etsy results by providing your own URLs to our service. We can return the HTML for any Etsy page you like. Additionally, we can deliver **structured (parsed) output for Etsy product pages**.

#### Python code example

The example below illustrates how you can get a parsed Etsy product page result.

```python
import requests
from pprint import pprint

# Structure payload.
payload = {
    'source': 'universal_ecommerce',
    'url': 'https://www.etsy.com/listing/524233279/tiny-silver-forget-me-not-earrings',
    'geo_location': 'United States',
    'parse': True,
}

# Get response.
response = requests.request(
    'POST',
    'https://realtime.oxylabs.io/v1/queries',
    auth=('user', 'pass1'),
    json=payload,
)

# Instead of response with job status and results url, this will return the
# JSON response with the result.
pprint(response.json())
```

Find code examples for other programming languages [**here**](https://github.com/oxylabs/etsy-scraper/tree/main/code%20examples)

#### Output Example
```json
{
    "results": [
        {
            "content": {
                "url": "https://www.etsy.com/listing/524233279/tiny-silver-forget-me-not-earrings?click_key=dee3e777ad5cc36010f708a8991825c7d84649b8:524233279&click_sum=2cca2059&ref=hp_rv-3&sts=1",
                "price": 29.48,
                "title": "Tiny silver Forget me Not earrings. Dainty sterling threader earrings with light blue enameled blossom. Threader Stud earring for her.",
                "images": [
                    "https://i.etsystatic.com/6401969/r/il/b84458/1226050351/il_75x75.1226050351_kvdw.jpg",
                    "https://i.etsystatic.com/6401969/c/1066/847/58/71/il/064963/1226057237/il_75x75.1226057237_q5jf.jpg",
                    "https://i.etsystatic.com/6401969/r/il/d68e0d/1226050373/il_75x75.1226050373_6u24.jpg",
                    "https://i.etsystatic.com/6401969/r/il/b71cfc/1226050549/il_75x75.1226050549_29un.jpg",
                    "https://i.etsystatic.com/6401969/r/il/fe8682/1178831922/il_75x75.1178831922_k9ny.jpg"
                ],
                "seller": {
                    "url": "https://www.etsy.com/shop/VillaSorgenfrei?ref=simple-shop-header-name&listing_id=524233279",
                    "title": "VillaSorgenfrei",
                    "rating": 4.8636,
                    "star_seller": true,
                    "reviews_count": 34115
                },
                "reviews": {
                    "count": 258
                },
                "currency": "USD",
                "shipping": {
                    "from": "Germany"
                },
                "categories": [
                    {
                        "title": "All categories"
                    },
                    {
                        "title": "Jewelry"
                    },
                    {
                        "title": "Earrings"
                    },
                    {
                        "title": "Stud Earrings"
                    }
                ],
                "product_id": "524233279",
                "stock_status": "Low in stock",
                "variation_count": 1,
                "parse_status_code": 12000
            },
            "created_at": "2022-11-17 14:45:28",
            "updated_at": "2022-11-17 14:45:33",
            "page": 1,
            "url": "https://www.etsy.com/listing/524233279/tiny-silver-forget-me-not-earrings?click_key=dee3e777ad5cc36010f708a8991825c7d84649b8:524233279&click_sum=2cca2059&ref=hp_rv-3&sts=1",
            "job_id": "6999019685052180481",
            "status_code": 200,
            "parser_type": "etsy_product"
        }
    ]
}
```

With our Etsy Scraper, you can effortlessly extract public data from any Etsy web page. Collect the required product information, such as price, reviews, or descriptions, to analyze the market and stay ahead of your competitors. If you have any questions, contact our support team via live chat or email us at hello@oxylabs.io.

Also, check this tutorial on [pypi](https://pypi.org/project/etsy-scraper-api/)
