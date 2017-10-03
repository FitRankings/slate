# Groups

## Get All Groups


```shell
curl "https://api.fitrankings.com/iq/groups/stat-summary/"
  -H "Authorization: Bearer MASTER_TOKEN"
```

> The above command returns JSON structured like this:

```json
{
  "group_id": 619,
  "avg_user_met_minutes": 11092.975341666666,
  "calories": 133191.6932,
  "activities": 188,
  "duration": 1129205.0, //seconds**
  "user_count": 12,
  "distance": 1205322.8494, //meters**
  "met_minutes": 133115.7041,
  "steps": 1155501
}
```

Retrieve aggregate stats for a group’s members.

### HTTP Request

`GET https://api.fitrankings.com/iq/groups/stat-summary/`

### Query Parameters

Parameter | Default | Format
--------- | ------- | -----------
time_mode | null | 1 = Year, 3 = Month, 4 = Week, 5 = Day
time_value | null | YYYY, YYYY-MM, YYYY-WWW, YYYY-MM-DD
start | null | YYYY-MM-DD HH:MM:SS
end | null | YYYY-MM-DD HH:MM:SS

<aside class="notice">
  Use either time_mode and time_value or start and end, in conjunction. If no parameters are provided, data will default to all-time stats. 
</aside>