# PTV API proojects 

A collection of projects that use the PTV API and some related files.

The main site is: 

https://www.ptv.vic.gov.au/footer/data-and-reporting/datasets/ptv-timetable-api/

# Swagger json file 

A description of the API and the swagger json file are here:

http://timetableapi.ptv.vic.gov.au/swagger/ui/index

## Updates 

The swagger json file is `v3.json` and the updated version is `v3_updated.json`

The updates: 
- removed the devid and signature parameters (as they are added by the client library after signature calculation)
- removed all the token parameters (as they has no use so just add noise)

## Fixes 

The json file describes the endpoint as returning an object of type `V3.RouteResponse`, which has a single `route` member of type `V3.RouteWithStatus` but the endpoint returns an object with member named `routes` that contains a list/array of `V3.RouteWithStatus`. 

I fixed this in the client library. 