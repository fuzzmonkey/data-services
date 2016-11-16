# data-services

## API Documentation

API Documentation is written using the swagger toolkit and can be viewed here:

http://petstore.swagger.io/?url=https://raw.githubusercontent.com/edbettech/data-services/master/swagger.json#/default

## Pull API Overview

The Pull API allows requests to be made for various sets of racing data. All requests must be made with the api_key header present in the request. It can be combined with the push API to receive real time updates of data changes.

### /meetings

Returns an array of meetings for a given date with each meeting including data down to the event level. The endpoint will default to returning today's meetings, today being the current date in UTC. This endpoint can be used to fetch a list of available meetings which can then polled for further data. 

Meetings are created throughout the day so it's important to poll this endpoint frequently.

### /meetings/{id}

Returns a meeting level detail for a given meeting including data down to the competitor level.

### /meetings/{id}/events/{event_id}/markets

Returns markets (e.g pools and exchange markets) for a given event in a meeting. 

### /meetings/{id}/events/{event_id}/results

Returns results including finish positions and payouts for a given event in a meeting. 

## Push API Overview

A push notifcation system can be configured to send updates to your server as data changes throughout the racing day. This updates include:

* New Meetings
* Event status changes (e.g OPEN > CLOSED > INTERIM > FINAL)
* Competitor Scratches
* Market changes (e.g latest tote prices, pool totals)
* Competitor Finish positions
* Market payouts (e.g tote pool results + payouts)
