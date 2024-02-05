# Registertovote Elections API [2024]

[<img src="img/logo.png" width="500"/>](img/logo.png)

---

*Developed by C.A Torino, TECHRAD Radical Technology*
* Links to TECHRAD ZA.
    * [Website](https://www.techrad.co.za)
    * [Tutorial website](https://tutorials.techrad.co.za)
    * [Support website](https://support.techrad.co.za)
    * [API](https://www.techrad.co.za/apisource/public/apps/fusio)


[<img src="img/qwefas321.jpg" width="500"/>](img/qwefas321.jpg)

The year is 2024 and South Africa is having an election year like many other countries.

I have compiled a list of a few useful API endpoints which allows someone to:

- view your current voter address.
- find your voting station.

Or simply to be aware of important information like upcoming election dates in your ward.

I have not included anything which could cause security issues like:

- register to vote
- update your current voter address
- request a special vote

For anything like that.. login to the https://registertovote.elections.org.za/Account/Login site.

This API is simply for checking stats.

## Check my registration status

Check to see if you are properly registered in the correct voting station.

go to: https://maps.elections.org.za/vsfinder/

## Endpoints

All work without needing to login

POST
GET

WORKS after logout
- {url}/IECGIS_VSFinder/api/autocomplete?
    - {parameters} = input=golden%20hill&guid=a1234qdsew3r534tgfd

WORKS after logout
- {url}/IECGIS_VSFinder/api/places?
    - {parameters} = placeid=EiZGYXJxdWhhciBSb2FkLCBMYWR5c21pdGgsIFNvdXRoIEFmcmljYSIuKiwKFAoSCaFOBrZMR_IeESdU8HrUV5FvEhQKEglJXdqRVUfyHhHAWV0W2DvXQw&guid=a58e1984-51a2-4d44-9228-aa7f2ac2e50e

WORKS after logout
- {url}/IECGIS_VSFinder/api/VotingDistrict?
    - {parameters} = latitude=-28.552764834140326&longitude=29.76976533135223

WORKS after logout
- {url}/IECGIS_VSFinder/api/Ward?
    - {parameters} = wardid=52308012

WORKS after logout
- {url}/IECGIS_VSFinder/api/Municipality?
    - {parameters} = municid=4462

WORKS after logout
- {url}/IECGIS_VSFinder/api/MEO?
    - {parameters} = municid=4462

## 1. Get Status

`Autocomplete Search return` [*Returns the details aboul the street address*]

{url} = https://gisapi.elections.org.za
- {url}/IECGIS_VSFinder/api/autocomplete? 
    - {parameters} = input=golden%20hill&guid=a1234qdsew3r534tgfd

-------------------

### Calling Parameters (Input)
| Parameter  |  Mode  | Description  | example values  |
| :------------ | :------------ | :------------ | :------------ |
|`input`  |string |search input   |golden hill |
|`guid`   |string |unique id      |a1234qdsew3r534tgfd |

### Interface Address

https://gisapi.elections.org.za/IECGIS_VSFinder/api/autocomplete? 

### Request Method

- HTTP
- POST

### Response Parameters (Output)
| Parameter  |  Mode  | Description  | example values  |
| :------------ | :------------ | :------------ | :------------ |
|`status`      |string      |Https        |OK    |
|`description` |string      |Https        |Golden Hills Estate, Smuts Drive, Halfway Gardens, Midrand, South Africa    |
|`placeid`     |string      |Https        |ChIJQarDjNJvlR4RLjGORId618Q    |
|`types`       |string      |Https        |establishment    |
|`guid`        |string      |Https        |a1234qdsew3r534tgfd    |


### Response Result Example
```JSON
{
   "status":"OK",
   "predictions":[
      {
         "description":"Golden Hill, Cape Town, South Africa",
         "placeid":"ChIJF4z7mJm1zR0R0ziu67uq7Dw",
         "types":[
            "sublocality_level_2",
            "sublocality",
            "political",
            "geocode"
         ],
         "guid":"a1234qdsew3r534tgfd"
      },
      {
         "description":"Golden Hills Estate, Smuts Drive, Halfway Gardens, Midrand, South Africa",
         "placeid":"ChIJQarDjNJvlR4RLjGORId618Q",
         "types":[
            "point_of_interest",
            "establishment"
         ],
         "guid":"a1234qdsew3r534tgfd"
      },
      {
         "description":"Golden Hills Garden, Matshekgeng, Makwane, Phuthaditjhaba, South Africa",
         "placeid":"ChIJUaJO9Eyx8h4RSgT_VRF03uU",
         "types":[
            "park",
            "point_of_interest",
            "establishment"
         ],
         "guid":"a1234qdsew3r534tgfd"
      },
      {
         "description":"Golden Hill Road, Northpine, Cape Town, South Africa",
         "placeid":"EjRHb2xkZW4gSGlsbCBSb2FkLCBOb3J0aHBpbmUsIENhcGUgVG93biwgU291dGggQWZyaWNhIi4qLAoUChIJO4UKj99TzB0RDSP6OK4FtrYSFAoSCSN0noNfUcwdEUXGfH2s3Yny",
         "types":[
            "route",
            "geocode"
         ],
         "guid":"a1234qdsew3r534tgfd"
      },
      {
         "description":"Golden Hill Guest House & Tours, Wilfried & Melanie Franke, Upper Mountain Road, Golden Hill, Cape Town, South Africa",
         "placeid":"ChIJaQQoZ5q1zR0ReGR7zNKOmxs",
         "types":[
            "lodging",
            "point_of_interest",
            "establishment"
         ],
         "guid":"a1234qdsew3r534tgfd"
      }
   ]
}
```

--------------------------------------------------------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------------------------------------------------------

## Endpoints

https://gisapi.elections.org.za/IECGIS_VSFinder/api/autocomplete?input=GoldenHill&guid=a1234qdsew3r534tgfd

https://gisapi.elections.org.za/IECGIS_VSFinder/api/places?placeid=ChIJQarDjNJvlR4RLjGORId618Q&guid=a1234qdsew3r534tgfd

https://gisapi.elections.org.za/IECGIS_VSFinder/api/VotingDistrict?latitude=-25.9949273697085&longitude=28.1144585302915

https://gisapi.elections.org.za/IECGIS_VSFinder/api/Ward?wardid=79800132

https://gisapi.elections.org.za/IECGIS_VSFinder/api/Municipality?municid=3003

https://gisapi.elections.org.za/IECGIS_VSFinder/api/MEO?municid=3003

## Gov API docs

https://gisapi.elections.org.za/iecgis_api/

Contact Centre
- [API Docs](https://gisapi.elections.org.za/IECGIS_ContactCentre)

ERS
- [API Docs](https://gisapi.elections.org.za/IECGIS_ERS)

VMD
- [API Docs](https://gisapi.elections.org.za/IECGIS_VMD)

Voter Portal
- [API Docs](https://gisapi.elections.org.za/IECGIS_Portal)

VRS
- [API Docs](https://gisapi.elections.org.za/IECGIS_VRS)

VS Finder
- [API Docs](https://gisapi.elections.org.za/IECGIS_VSFinder)

Political Parties/Media
- [API Docs](https://api.elections.org.za/IECGIS)
