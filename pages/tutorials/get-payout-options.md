---
layout: default
title: Get Payout Options
toc: tutorial-get-payout-options
body_color: body-orange
section_name: Get Payout Options
last_updated: September 23rd, 2019
icon_class: icon_documents_alt icon
breadcrumbs: "Tutorials,tutorials"
---
# Get Payout Options
The payout options are what you may need to present to your customer as part of the payout process you are developing.

For more information on the getting payout options, see the [Payout Options in Getting Started](/pages/getting-started/payout-options).

# Prerequisites
In addition to familiarity with the [Core Concepts](/pages/guides/core-concepts), you'll need the following:

 A valid `Access Token` derived from a `Tenant API Key`

# Get the Payout Options
Using the `Access Token` we can get the Payout Options.

#### Request
Replace the `{access-token}` placeholder value with the `Access Token` value.

```curl
curl --location --request GET "https://sandbox-api.imbursepayments.com/v1/schemes/payout/{schemeId}/options?amount=10.00&currency=EUR&country=DE&matchType=Exact" \
  --header "Authorization: Bearer {access-token}"
```

##### The MatchType parameter
The `matchType` parameter on the request determines how the **Fixed** value rewards are matched against the requested amount parameter. 

**Note: The default Match Type value if not specified on the URL will be `Exact`.**

Value | Description
-|-
`Exact` | For Fixed value rewards, the requested amount must match the reward fixed value.<br/><br/>For Variable value rewards, the requested amount must be within reward value range.
`Max`   | For Fixed value rewards, the reward value must be less than OR equal to the requested amount.<br/><br/>For Variable value rewards, the requested amount must be within reward value range.


#### Response
The response will contain all the rewards appropriate for the customers payment instruction. Please note, for brevity in this tutorial we are only showing 1 result.

```json
{
  "rewards": [
    {
      "rewardId": "6a30bdaa-483a-2b3f-e28e-0158d0cf07c2",
      "rewardName": "Amazon.de Kupony",
      "rewardType": "gift card",
      "status": "active",
      "countries": [
        "PL"
      ],
      "currencyCode": "EUR",
      "exchangeRateRule": null,
      "isWholeAmountValueRequired": false,
      "valueType": "VARIABLE_VALUE",
      "fixedValue": null,
      "maxValue": 5000,
      "minValue": 0.01,
      "credentialTypes": [
        "cardNumber",
        "expirationDate"
      ],
      "redemptionInstructions": "<p><strong>Aby zrealizować kupon, wykonaj następujące czynności:</strong></p>\r\n\r\n<ol>\r\n\t<li>Przejdź na stronę&nbsp;<a href=\"https://translate.google.com/translate?hl=en&amp;prev=_t&amp;sl=auto&amp;tl=pl&amp;u=http://www.amazon.de/Geschenkgutscheine/b%3Fie%3DUTF8%26node%3D1571256031\">www.amazon.de/gp/gc</a>.&nbsp;Kliknij &quot;&nbsp;Wykorzystaj kupon&nbsp;&quot; i&nbsp;po wyświetleniu monitu&nbsp;wpisz&nbsp;kod&nbsp;kuponu&nbsp;.</li>\r\n\t<li>Kwoty kupon&oacute;w są automatycznie dodawane do kwalifikujących się zam&oacute;wień podczas procesu anulowania subskrypcji.</li>\r\n\t<li>Pozostałe kwoty r&oacute;żnic w zam&oacute;wieniu należy uregulować inną metodą płatności.</li>\r\n</ol>\r\n\r\n<p>Możesz&nbsp;także wpisać kod&nbsp;kuponu,&nbsp;jeśli pojawi się monit podczas procesu wypisania się.&nbsp;Odkupienie vouchera nie jest jednak możliwe w przypadku korzystania z usługi&nbsp;<a href=\"http://www.amazon.de\">Amazon.de</a>&nbsp;1-Click&reg;, chyba że pierwszy raz wykorzystasz kupon za pośrednictwem swojego konta.</p>\r\n\r\n<p><strong>To redeem the code, please proceed as follows:</strong></p>\r\n\r\n<ol>\r\n\t<li>Go to&nbsp;<a href=\"https://translate.google.com/translate?hl=en&amp;prev=_t&amp;sl=auto&amp;tl=en&amp;u=http://www.amazon.de/Geschenkgutscheine/b%3Fie%3DUTF8%26node%3D1571256031\">www.amazon.de/gp/gc</a>.&nbsp;Click &quot;Redeem Gift Card&quot; and enter the&nbsp;Claim Code when prompted.</li>\r\n\t<li>Gift Card amounts will be applied automatically to eligible orders during the checkout process.</li>\r\n\t<li>You must pay for any remaining balance on your order with another payment method.</li>\r\n</ol>\r\n\r\n<p>Your gift card claim code may also be entered when prompted during the checkout process but you will not be able to redeem your gift card using the&nbsp;<a href=\"http://amazon.de/\">Amazon.de</a>&nbsp;1-Click&reg; service or downloadable e-books unless you first redeem the gift card through Your Account.</p>\r\n",
      "tags": [],
      "app": {
        "appId": "TANGOCARD_RAAS",
        "name": "tangocard_raas - todo: schema needs to be defined."
      },
      "brand": {
        "brandKey": "B050503",
        "brandName": "Amazon.de Poland",
        "status": "active",
        "description": "<p>Kupony&nbsp;<a href=\"http://amazon.de/\">Amazon.de</a>&nbsp;można liczyć na miliony artykuł&oacute;w na stronie&nbsp;<a href=\"http://www.amazon.de/\">www.amazon.de</a>&nbsp;i niekt&oacute;rych witrynach stowarzyszonych. Ogromny wyb&oacute;r&nbsp;<a href=\"http://amazon.de/\">Amazon.de</a>&nbsp;obejmuje produkty w kategoriach książek, elektroniki, muzyki, plik&oacute;w MP3, film&oacute;w i telewizja, odzież, gry wideo, oprogramowanie, sport i na zewnątrz, zabawki, niemowlę, komputer i biuro, dom i ogr&oacute;d, biżuteria, uroda, majsterkowanie, artykuły biurowe, aparat fotograficzny i fotograficzny, akcesoria dla zwierząt i nie tylko.&nbsp;<a href=\"http://ammazon.com/\">A</a><a href=\"http://www.Amazon.de\">mazon.de</a>&nbsp;to miejsce, w kt&oacute;rym znajduj i odkrywaj prawie wszystko, co chcesz kupić online po konkurencyjnej cenie.&nbsp;</p>\r\n\r\n<p><a href=\"http://amazon.de/\">Amazon.de</a>&nbsp;Gift Cards* can be redeemed towards millions of items at&nbsp;<a href=\"http://www.amazon.de/\">www.amazon.de</a>.&nbsp;<a href=\"http://amazon.de/\">Amazon.de</a>&rsquo;s huge selection includes products in Books, Electronics, Music, MP3 Downloads, Film &amp; TV, Clothing, Video Games, Software, Sports &amp; Outdoors, Toys, Baby, Computers &amp; Office, Home &amp; Garden, Jewelry, Beauty, DIY &amp; Home Improvement, Office Products, Camera &amp; Photo, Pet Supplies, and more.&nbsp;<a href=\"http://amazon.de/\">Amazon.de</a>&nbsp;is the place to find and discover almost anything you want to buy online at a great price.</p>\r\n",
        "shortDescription": "<p>Kupony&nbsp;<a href=\"http://amazon.de/\">Amazon.de</a>&nbsp;można zaliczyć do milion&oacute;w artykuł&oacute;w na stronie&nbsp;<a href=\"http://www.amazon.de/\">www.amazon.de</a>.</p>\r\n\r\n<p><a href=\"http://amazon.de/\">Amazon.de</a>&nbsp;Gift Cards* can be redeemed towards millions of items at&nbsp;<a href=\"http://www.amazon.de/\">www.amazon.de</a>.</p>\r\n",
        "disclaimer": "<p>*Obowiązują ograniczenia. Pełne warunki korzystania z usługi można znaleźć na stronie: <a href=\"http://www.amazon.de/gc-legal\">amazon.de/gc-legal</a></p>\r\n\r\n<p>*Restrictions apply. For complete terms and conditions, visit:&nbsp;<a href=\"http://www.amazon.de/gc-legal\">amazon.de/gc-legal</a></p>\r\n",
        "terms": "<p>*Obowiązują ograniczenia. Pełne warunki korzystania z usługi można znaleźć na stronie: <a href=\"http://www.amazon.de/gc-legal\">amazon.de/gc-legal</a></p>\r\n\r\n<p>*Restrictions apply. For complete terms and conditions, visit:&nbsp;<a href=\"http://www.amazon.de/gc-legal\">amazon.de/gc-legal</a></p>\r\n",
        "imageUrls": [
          {
            "ppi": 326,
            "url": "https://dwwvg90koz96l.cloudfront.net/images/brands/b050503-80w-326ppi.png",
            "width": 80
          },
          {
            "ppi": 326,
            "url": "https://dwwvg90koz96l.cloudfront.net/images/brands/b050503-130w-326ppi.png",
            "width": 130
          },
          {
            "ppi": 326,
            "url": "https://dwwvg90koz96l.cloudfront.net/images/brands/b050503-200w-326ppi.png",
            "width": 200
          },
          {
            "ppi": 326,
            "url": "https://dwwvg90koz96l.cloudfront.net/images/brands/b050503-278w-326ppi.png",
            "width": 278
          },
          {
            "ppi": 326,
            "url": "https://dwwvg90koz96l.cloudfront.net/images/brands/b050503-300w-326ppi.png",
            "width": 300
          },
          {
            "ppi": 326,
            "url": "https://dwwvg90koz96l.cloudfront.net/images/brands/b050503-1200w-326ppi.png",
            "width": 1200
          }
        ],
        "requirements": {
          "alwaysShowDisclaimer": false,
          "disclaimerInstructions": "",
          "displayInstructions": "",
          "termsAndConditionsInstructions": ""
        }
      },
      "createdDate": "2019-06-04T16:25:39.4803963",
      "lastUpdateDate": "2019-06-04T16:25:39.4803964"
    }
  ]
}
```

# What's Next?
- [Claiming a Reward](/pages/tutorials/claiming-a-reward)
