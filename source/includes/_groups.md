# Groups

## Get A Group's Stat Summary


```shell
curl "https://api.fitrankings.com/iq/groups/stat-summary/" \
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

### URL Parameters

Parameter | Default | Format
--------- | ------- | -----------
time_mode | 0 (all-time) | The period to aggregate stats for. 1 = Year, 3 = Month, 4 = Week, 5 = Day. Optional.
time_value | NA | The time period to use in conjunction with the time_mode. YYYY, YYYY-MM, YYYY-WWW, YYYY-MM-DD. Optional.
start | NA | YYYY-MM-DD HH:MM:SS
end | NA | YYYY-MM-DD HH:MM:SS

<aside class="notice">
  Use either time_mode and time_value or start and end, in conjunction. If no parameters are provided, data will default to all-time stats. 
</aside>