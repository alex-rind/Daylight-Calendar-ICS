# Daylight Calendar ICS

This is a dynamically generated .ics calendar that you can host and subscribe to in Google Calendar, iCal, or other calendar software.

This will create two events for each day of the current year:
- The sunrise event extends from nautical twilight to the given zenith setting.
- The sunset event extends from the given zenith setting to nautical twilight.
In the sunrise's description, it will show the length of the day in hours/minutes as well as in a percent (of 24 hours). It will also give a percentile compared to the shortest and longest days of the year!

## Options

- [Find your geo coordinates](http://mygeoposition.com/)
- [Find your GMT offset](http://en.wikipedia.org/wiki/List_of_UTC_time_offsets#mediaviewer/File:World_Time_Zones_Map.png)
- Determine which zenith setting you prefer
  - Default: `90.83`
  - Civil Twilight: `96`
    - _Conventionally used to signify twilight_
  - Nautical Twilight: `102`
    - _The point at which the horizon stops being visible at sea_
  - Astronomical Twilight: `108`
    - _The point when Sun stops being a source of any illumination_
    
## Instructions

- Upload `daylight.php` to your server.
- Point your calendar to the file and use query parameters for the options above.
  - Latitude: `lat`
  - Longitude: `lng`
  - GMT: `gmt`
  - Zenith: `z`
  - Year: `year`
  - Location: `loc` (optional; just displayed)

Use `?debug` to directly view the calendar file in a browser with events more easily readable. Be sure not to use `?debug` when subscribing to your calendar as it does not declare itself as an .ics file with that parameter present.

## Examples

#### Basic
`https://gearside.com/calendars/daylight.php?lat=43.1234&lng=-76.1234&gmt=-5`


#### Advanced
`https://gearside.com/calendars/daylight.php?lat=43.1234&lng=-76.1234&gmt=-5&z=108`

`https://localhost:8080/calendars/daylight.php?lat=48.2&lng=16.4&gmt=1&loc=Wien`

## Notes

Calendar software caches remote .ics files (like this one), so when replacing it you can "bust" the cache by adding another query parameter of random characters such as `&sdfgsfd`.

- [More information available at Gearside.com](https://gearside.com/google-daylight-calendar/)