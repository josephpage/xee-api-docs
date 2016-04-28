# /trips/{tripId}/locations

Get the locations history from a specific *trip as a [Geojson LineString](http://geojson.org/geojson-spec.html#id3)*

## Basics

`[GET] https://cloud.xee.com/v3/trips/{tripId}/locations.geojson`

> You'll need the, *trips_read* and *locations_read* scope.

Secured by **OAuth 2** access token.

## Request

### Headers

|Header name|Header value|Mandatory|
|---|---|---|
|Authorization|`Bearer` with the *OAuth2* access token|YES|

### Url Parameters

|Parameter name|Parameter value|Mandatory|
|---|---|---|
|`tripId`|The `id` of the *trip* you are looking for the *locations*|YES|

## Success Response

- Status Code: `200`
- Body:

```javascript 
{"type":
	"LineString",
	"coordinates":[
		[3.0580485,50.632244]
		...
	]
}
```



|Property|Type|Comment|
|---|---|---|
|type|string|The type of the Geojson object|
|coordinates|array|Array of Array of Points of the trip (longitude, latitude)|

## Errors

> See how errors are formed in [v3 Readme](../README.md)

> Be aware of [authentication errors](../auth/README.md)

|Reason|Status Code|Type|Message|Tip|
|---|---|---|---|---|
|The token does not have access to this trip|`403`|`AUTHORIZATION_ERROR`|Token can't access this trip|Make sure the trip belongs to the user you've got the token from|
|Trip does not exist|`404`|`PARAMETERS_ERROR`|Trip not found|Please check that the trip exists, looks like it does not|