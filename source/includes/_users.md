# Users

## Get All Users


```shell
curl "https://api.fitrankings.com/iq/users/"
  -H "Authorization: Bearer YOUR_TOKEN"
```

> The above command returns JSON structured like this:

```json
[{
    "id": 30267,
    "email": "aaron@smith.com",
    "first_name": "Aaron",
    "last_name": "Smith",
    "date_joined": "2017-08-07T19:11:51.971815Z",
    "handle": null
  }, …]
```

Retrieve a list of all activities related to a user or client (ordered by date).

### HTTP Request

`GET https://api.fitrankings.com/iq/users/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | The page to jump to. Optional.
page_size | 20 | The amount of results to include per page. Optional.

## Get a User's Stat Summary

```shell
curl "https://api.fitrankings.com/iq/users/stat-summary/"
  -H "Authorization: Bearer YOUR_TOKEN"
```

> The above command returns JSON structured like this:

```json
{
    "calories": 46272.1676,
    "duration": 381845.0, //seconds**
    "distance": 766966.1322, //meters**
    "user_id": 30264,
    "met_minutes": 42186.1016,
    "steps": 713047
  }
```

This endpoint retrieves a user's aggregate stats for the given time period. 

### HTTP Request

`GET https://api.fitrankings.com/iq/users/stat-summary/`

### URL Parameters

Parameter | Default | Description
--------- | ------- | -----------
time_mode | 0 (all-time) | The period to aggregate stats for. 1 = Year, 3 = Month, 4 = Week, 5 = Day. Optional.
time_value | NA | The time period to use in conjunction with the time_mode. YYYY, YYYY-MM, YYYY-WW, YYYY-MM-DD. Optional.
start | NA | YYYY-MM-DD HH:MM:SS Optional.
end | NA | YYYY-MM-DD HH:MM:SS Optional.

<aside class="notice">
  Use either time_mode and time_value or start and end, in conjunction. If no parameters are provided, data will default to all-time stats. 
</aside>