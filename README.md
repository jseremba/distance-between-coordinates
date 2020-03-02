# distance-between-coordinates
Calculates distance between coordinates

```function distanceBetweenCoordinates(lon1, lon2, lat1, lat2) {
	widget.logWrite(WIDGET_LOG_LEVEL,MSISDN_LOG+"REQUEST ENTERED distanceBetweenCoordinates ###");
	widget.logWrite(WIDGET_LOG_LEVEL,MSISDN_LOG+": "+lon1+" : "+lon2+" : "+lat1+" : "+lat2);
	var R = 6371; // Radius of the earth in km
	var dLat = deg2rad(lat2 - lat1); // deg2rad below
	var dLon = deg2rad(lon2 - lon1);
	var a =
		Math.sin(dLat / 2) * Math.sin(dLat / 2) +
		Math.cos(deg2rad(lat1)) * Math.cos(deg2rad(lat2)) *
		Math.sin(dLon / 2) * Math.sin(dLon / 2);
	var c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));
	var d = R * c; // Distance in km	  
	widget.logWrite(WIDGET_LOG_LEVEL,MSISDN_LOG+"REQUEST PROCESSED distanceBetweenCoordinates ###"+" "+d);
	return d;
}
