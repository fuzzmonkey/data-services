# data-services

## API Documentation

Visit this link and click 'default' to view the API documentation.

http://petstore.swagger.io/?url=https://raw.githubusercontent.com/edbettech/data-services/master/swagger.json#/

## Overview

All requests must be made with the api_key header present in the request.

### /meetings

Returns an array of meetings for a given date with each meeting including data down to the event level. The endpoint will default to returning today's meetings, today being the current date in UTC. This endpoint can be used to fetch a list of available meetings which can then polled for further data. 

Meetings are created throughout the day so it's important to poll this endpoint frequently.

### /meetings/{id}

Returns a meeting level detail for a given meeting including data down to the competitor level.

### /meetings/{id}/events/{event_id}/markets

Returns markets (e.g pools and exchange markets) for a given event in a meeting. 

### /meetings/{id}/events/{event_id}/results

Returns results including finish positions and payouts for a given event in a meeting. 
