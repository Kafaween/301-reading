# Location

- Using the Google Play services location APIs, your app can request the last known location of the user's device
- make a single request for the location of a device using the getLastLocation() method in the fused location provider.

## Set up Google Play services

- Download and install the Google Play services component via the SDK Manager and add the library to your project.

## Specify app permissions

- Apps whose features use location services must request location permissions, depending on the use cases of those features.

## Create location services client

- In your activity's onCreate() method ,create:

```private FusedLocationProviderClient fusedLocationClient;

// ..

@Override
protected void onCreate(Bundle savedInstanceState) {
    // ...

    fusedLocationClient = LocationServices.getFusedLocationProviderClient(this);
}

```

## Get the last known location

- To request the last known location, call the getLastLocation() method. The following code snippet illustrates the request and a simple handling of the response:

```fusedLocationClient.getLastLocation()
        .addOnSuccessListener(this, new OnSuccessListener<Location>() {
            @Override
            public void onSuccess(Location location) {
                // Got last known location. In some rare situations this can be null.
                if (location != null) {
                    // Logic to handle location object
                }
            }
        });


```

* The getLastLocation() method returns a Task that you can use to get a Location object with the latitude and longitude coordinates of a geographic location. 
* The location object may be null in the following situations: 
1. Location is turned off in the device settings. 
2. The device never recorded its location
3. Google Play services on the device has restarted
