# Devices

Interact with device. These routes are quite private, and the required scope to call them is not accessible to all the applications.

> Don't forget the *devices_management* scope.

|API|Description|
|---|---|
|[`POST /devices/{xeeId}/associate?carId={carId}`](associate_car.md)|Associate a car to the given device|
|[`POST /devices/{xeeId}/associate?pin={pin}`](associate_user.md)|Associate a user to the given device|
|[`POST /devices/{xeeId}/dissociate`](dissoiate.md)|Dissociate the given device from it's car|