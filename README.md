[https://apify.com/epctex/soundcloud-scraper](https://apify.com/epctex/soundcloud-scraper?fpr=yhdrb)

# Actor - SoundCloud Scraper

## SoundCloud scraper

Since SoundCloud doesn't provide a good and free API, this actor should help you to retrieve data from it.

The SoundCloud data scraper supports the following features:

-   Search any keyword - Search for any keywords with no rate limit and retrieve the results with ease.

-   Search for users, tracks, playlists, or albums - Filter your search results by object type. Albums, Playlists, Tracks, and Users are available for any search.

-   Get tracks - ID, title, duration, user information, monetization models, repost or like counts, and many other deep-level information is ready for your consumption.

-   Tracks available for download - Get the download URLs for the SoundCloud tracks.

-   Comments for each of the tracks - Looking for user comments? No problem. Retrieve all the comments, dates, user information, and many other things blazing fast!

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/soundcloud-scraper/issues).


## Input Parameters

The input of this scraper should be JSON containing the list of pages on SoundCloud that should be visited. Possible fields are:

- `startUrls`: (Required) (Array) List of SoundCloud URLs. URLs to start with. It should be a list, search, track, user, album, or playlist URL.

- `includeComments`: (Optional) (Boolean) This will add all the comments that SoundCloud provides into the track objects. Please keep in mind that the time and resources the actor uses will increase proportionally to the number of comments.

- `endPage`: (Optional) (Number) Final number of page that you want to scrape. The default is `Infinite`. This applies to all `search` requests and `startUrls` individually.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

When you want to scrape over a specific list URL, just copy and paste the link as one of the **startUrl**.

If you would like to scrape only the first page of a list then put the link for the page and have the `endPage` as 1.

With the last approach that is explained above you can also fetch any interval of pages. If you provide the 5th page of a list and define the `endPage` parameter as 6 then you'll have the 5th and 6th pages only.

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape as many items as possible. Therefore, it forefronts all the detailed requests. If the actor doesn't block very often it'll scrape 100 tracks in 2 minutes with ~0.01-0.03 compute units.

### SoundCloud Scraper Input example

```json
{
  "startUrls":[
    "https://soundcloud.com/sibel-dar-c/ekin-ekinci-gel-art-k",
    "https://soundcloud.com/sibel-dar-c",
    "https://soundcloud.com/swedish-hiphop-rap-fm/sets/pistoler-poesi-och-sex",
    "https://soundcloud.com/search/sets?q=dnb",
    "https://soundcloud.com/search/people?q=dnb",
    "https://soundcloud.com/search/albums?q=dnb",
    "https://soundcloud.com/search/sounds?q=dnb"
  ],
  "endPage":3,
  "maxItems":20,
  "includeComments":false,
  "proxy":{
    "useApifyProxy":true
  }
}
```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## SoundCloud Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this SoundCloud actor.

## Scraped SoundCloud Properties

The structure of each item in SoundCloud looks like this:

```json
{
    "artwork_url": "https://i1.sndcdn.com/artworks-KUd5CFXdByl4gCVn-qYc5Ug-large.jpg",
    "caption": null,
    "commentable": true,
    "comment_count": 754,
    "created_at": "2023-01-24T13:15:38Z",
    "description": "🚨SUBSCRIBE: bit.ly/DnbaSubscribe\n\n🎫 360 SIGN UP: https://t.me/dnballstars360\n\n📲FOLLOW: @dnballstars\n\n📰VISIT: dnballstars.co.uk\n\n🎧PLAYLISTS: lnk.to/DNBA-hotpick\n\n💡Enable Alerts 💥",
    "downloadable": false,
    "download_count": 0,
    "duration": 3558922,
    "full_duration": 3558922,
    "embeddable_by": "all",
    "genre": "Drum & Bass",
    "has_downloads_left": false,
    "id": 1431326908,
    "kind": "track",
    "label_name": null,
    "last_modified": "2023-03-13T21:42:46Z",
    "license": "all-rights-reserved",
    "likes_count": 13904,
    "permalink": "hedex-dnb-allstars-360",
    "permalink_url": "https://soundcloud.com/dnballstars/hedex-dnb-allstars-360",
    "playback_count": 307681,
    "public": true,
    "publisher_metadata": {
        "id": 1431326908,
        "urn": "soundcloud:tracks:1431326908",
        "artist": "",
        "contains_music": true
    },
    "purchase_title": "JOIN US",
    "purchase_url": "https://t.me/dnballstars360",
    "release_date": null,
    "reposts_count": 507,
    "secret_token": null,
    "sharing": "public",
    "state": "finished",
    "streamable": true,
    "tag_list": "",
    "title": "Hedex - DnB Allstars 360°",
    "track_format": "single-track",
    "uri": "https://api.soundcloud.com/tracks/1431326908",
    "urn": "soundcloud:tracks:1431326908",
    "user_id": 366752855,
    "visuals": null,
    "waveform_url": "https://wave.sndcdn.com/AExJj2NYeBEy_m.json",
    "display_date": "2023-01-24T19:00:18Z",
    "media": {
        "transcodings": [
            {
                "url": "https://api-v2.soundcloud.com/media/soundcloud:tracks:1431326908/c75cef09-1ef2-46ea-b8a2-d9b1740eaa56/stream/hls",
                "preset": "mp3_1_0",
                "duration": 3558922,
                "snipped": false,
                "format": {
                    "protocol": "hls",
                    "mime_type": "audio/mpeg"
                },
                "quality": "sq"
            },
            {
                "url": "https://api-v2.soundcloud.com/media/soundcloud:tracks:1431326908/c75cef09-1ef2-46ea-b8a2-d9b1740eaa56/stream/progressive",
                "preset": "mp3_1_0",
                "duration": 3558922,
                "snipped": false,
                "format": {
                    "protocol": "progressive",
                    "mime_type": "audio/mpeg"
                },
                "quality": "sq"
            },
            {
                "url": "https://api-v2.soundcloud.com/media/soundcloud:tracks:1431326908/2b7c6c4a-2bce-465d-8254-5b440e662328/stream/hls",
                "preset": "opus_0_0",
                "duration": 3558895,
                "snipped": false,
                "format": {
                    "protocol": "hls",
                    "mime_type": "audio/ogg; codecs=\"opus\""
                },
                "quality": "sq"
            }
        ]
    },
    "station_urn": "soundcloud:system-playlists:track-stations:1431326908",
    "station_permalink": "track-stations:1431326908",
    "track_authorization": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJnZW8iOiJUUiIsInN1YiI6IiIsInJpZCI6IjEwMmU5MWEwLTNkOWEtNGM0ZC04OTllLTZlMTIwZDM2YWRhMCIsImlhdCI6MTY3OTQ3NTA1Mn0.abKMM2OF_Xh4-JDtM4vEFDzJqQiNPQq7dp027Nc6_KQ",
    "monetization_model": "NOT_APPLICABLE",
    "policy": "ALLOW",
    "user": {
        "avatar_url": "https://i1.sndcdn.com/avatars-000367648727-gp601z-large.jpg",
        "first_name": "",
        "followers_count": 84897,
        "full_name": "",
        "id": 366752855,
        "kind": "user",
        "last_modified": "2023-03-20T12:53:28Z",
        "last_name": "",
        "permalink": "dnballstars",
        "permalink_url": "https://soundcloud.com/dnballstars",
        "uri": "https://api.soundcloud.com/users/366752855",
        "urn": "soundcloud:users:366752855",
        "username": "DnB Allstars",
        "verified": true,
        "city": "London",
        "country_code": null,
        "badges": {
            "pro": false,
            "pro_unlimited": true,
            "verified": true
        },
        "station_urn": "soundcloud:system-playlists:artist-stations:366752855",
        "station_permalink": "artist-stations:366752855"
    },
    "comments": [
        {
            "kind": "comment",
            "id": 1900670014,
            "body": "Oh my days 😳😳😳",
            "created_at": "2023-03-16T17:34:43Z",
            "timestamp": 326931,
            "track_id": 1431326908,
            "user_id": 199049081,
            "self": {
                "urn": "soundcloud:comments:1900670014"
            },
            "user": {
                "avatar_url": "https://a1.sndcdn.com/images/default_avatar_large.png",
                "first_name": "",
                "followers_count": 7,
                "full_name": "",
                "id": 199049081,
                "kind": "user",
                "last_modified": "2023-03-16T17:34:38Z",
                "last_name": "",
                "permalink": "user-655659681",
                "permalink_url": "https://soundcloud.com/user-655659681",
                "uri": "https://api.soundcloud.com/users/199049081",
                "urn": "soundcloud:users:199049081",
                "username": "User 655659681",
                "verified": false,
                "city": null,
                "country_code": null,
                "badges": {
                    "pro": false,
                    "pro_unlimited": false,
                    "verified": false
                },
                "station_urn": "soundcloud:system-playlists:artist-stations:199049081",
                "station_permalink": "artist-stations:199049081"
            }
        },
        {
            "kind": "comment",
            "id": 1900505365,
            "body": "🧐🧐🧐🧐",
            "created_at": "2023-03-16T11:42:41Z",
            "timestamp": 124858,
            "track_id": 1431326908,
            "user_id": 1051717858,
            "self": {
                "urn": "soundcloud:comments:1900505365"
            },
            "user": {
                "avatar_url": "https://i1.sndcdn.com/avatars-m0rsLpyetcHHc00w-yXkOwA-large.jpg",
                "first_name": "",
                "followers_count": 4,
                "full_name": "",
                "id": 1051717858,
                "kind": "user",
                "last_modified": "2023-01-13T09:42:44Z",
                "last_name": "",
                "permalink": "user-172639176",
                "permalink_url": "https://soundcloud.com/user-172639176",
                "uri": "https://api.soundcloud.com/users/1051717858",
                "urn": "soundcloud:users:1051717858",
                "username": "tommymoore05",
                "verified": false,
                "city": "",
                "country_code": "GB",
                "badges": {
                    "pro": false,
                    "pro_unlimited": false,
                    "verified": false
                },
                "station_urn": "soundcloud:system-playlists:artist-stations:1051717858",
                "station_permalink": "artist-stations:1051717858"
            }
        },
    ]
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [business@epctex.com](mailto:business@epctex.com) is at your service.
