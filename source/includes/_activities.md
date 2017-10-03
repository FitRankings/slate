# Activities

## Get All Activities


```shell
curl "https://api.fitrankings.com/iq/activities/" \
  -H "Authorization: Bearer USER_OR_MASTER_TOKEN"
```

> The above command returns JSON structured like this:

```json
[{
      "id": 685612,
      "title": null,
      "description": null,
      "met_minutes": "23.0000",
      "distance": "16009.3440", //meters**
      "duration": "600.0000", //seconds**
      "steps": 111,
      "calories": "22.0000",
      "provider_image_url": null,
      "provider_key": "fitbit",
      "provider_activity_id": "8222125504",
      "activity_type": "1",
      "fitness_type": "2",
      "action_date": "2017-06-13T12:00:00Z",
      "is_locked": false,
      "is_edited": false,
      "is_manual_entry": false,
      "is_deleted": false,
      "created_at": "2017-06-23T17:14:28.840028Z",
      "updated_at": "2017-06-23T17:14:28.840053Z",
      "user": {
        "id": 30171,
        "email": "john@gmail.com",
        "first_name": "John",
        "last_name": "Smith",
        "date_joined": "2017-06-23T17:14:10.995721Z",
        "handle": null,
        "profile": {
          "id": 10494,
          "display_name": "J. Smith",
          "display_name_format": "0",
          "image_profile_url": null,
          "is_private": false,
          "follower_count": 0,
          "following_count": 0,
          "bio": null
        }
      },
      "current_user_reacted_with_type": -1,
      "like_count": 0,
      "comment_count": 0,
      "comments": []
    }, ...]
```

Retrieve a list of all activities related to a user or client (ordered by date).

### HTTP Request

`GET https://api.fitrankings.com/iq/activities/`

### URL Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | The page to jump to. Optional.
page_size | 20 | The amount of results to include per page. Optional.

## Get a Specific Activity

```shell
curl "https://api.fitrankings.com/iq/activities/<ID>/" \
  -H "Authorization: Bearer USER_OR_MASTER_TOKEN"
```

> The above command returns JSON structured like this:

```json
{
  "id": 685775,
  "title": null,
  "description": null,
  "met_minutes": "182.0000",
  "distance": "0.0000", //meters**
  "duration": "5460.0000", //seconds**
  "steps": 3347,
  "calories": "0.0000",
  "provider_image_url": null,
  "provider_key": "google-oauth2",
  "provider_activity_id": "1502064788614000000",
  "activity_type": "1",
  "fitness_type": "1",
  "action_date": "2017-08-07T00:00:00Z",
  "is_locked": false,
  "is_edited": false,
  "is_manual_entry": false,
  "is_deleted": false,
  "created_at": "2017-08-08T17:08:24.310110Z",
  "updated_at": "2017-08-08T17:08:24.310137Z",
  "user": {
    "id": 30264,
    "email": "bob@aol.com",
    "first_name": "Bob",
    "last_name": "Smith",
    "date_joined": "2017-06-21T17:52:32.795423Z",
    "handle": null,
    "profile": {
      "id": 10493,
      "display_name": "Bob",
      "display_name_format": "1",
      "image_profile_url": "https://d2qqvi7evhy56u.cloudfront.net/c19757295d946c50e1117f2b34a1481373516c4a.png",
      "is_private": false,
      "follower_count": 0,
      "following_count": 0,
      "bio": null
    }
  },
  "current_user_reacted_with_type": -1,
  "like_count": 0,
  "comment_count": 0,
  "comments": []
}

```

This endpoint retrieves a specific activity by id.

### HTTP Request

`GET https://api.fitrankings.com/iq/activities/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the activity to retrieve.