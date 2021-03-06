# Location and Fake Location Detector 

<img align="center" src='https://github.com/balrampandey19/FakeLocationDetctor/blob/master/Screen/loc8.png' width='200' height='200'/>

Loc8 is a android location manager library to get accurate location simply.

This libray use [Android LocationManager](https://developer.android.com/reference/android/location/LocationManager.html)  and very cool and optimized Google play service location provider api [FusedLocationProvider](https://developers.google.com/android/reference/com/google/android/gms/location/FusedLocationProviderApi) uses a mix of hardware to determine location based on the context of the request, meaning it's optimized transparently to you. It will also cache captured locations between applications to avoid unnecessary work to determine location info. So if a user has a variety of location-aware apps, they potentially avoid taxing the device (and waiting) for a location capture as one may have already been cached.
## By using Loc8 you can get

* Get accurate current location.
* Check is locktion is Mocked.
* Check whether the application has required permission or not
* Check whether GPS Provider is enabled or not
* Check whether Network Provider is enabled or not
* if location not available you can get LastKnown location

# Usage

## Permission
Don't forget to add the following permissions to your AndroidManifest.xml

```
 <uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />

```

#### Get location with Loc8.DEFAULT TAG

By Using <b>Loc8.DEFAULT</b> TAG library check if Google play service is available, if available library access location using <b>FusedLocationProvider</b> and if Google play service not available library access location using Android default <b>Location Manager</b>

```
  Loc8 loc8 = Loc8.getInstance(mcontext, Loc8.DEFAULT);
        loc8.getLocation(new LocationCallback() {
            @Override
            public void onError(String error) {
               }
            @Override
            public void onSuccess(Location location) {
              }
        });

```
#### Get location with Loc8.Loc8.LOCATION_API TAG
By Using <b>Loc8.LOCATION_API</b> TAG library access location using <b>FusedLocationProvider</b> and if google play service not available return error.

```
  Loc8 loc8 = Loc8.getInstance(mcontext, Loc8.DEFAULT);
        loc8.getLocation(new LocationCallback() {
            @Override
            public void onError(String error) {
               }
            @Override
            public void onSuccess(Location location) {
              }
        });

```
#### Get location with Loc8.Loc8.LOCATION_MANAGER TAG
By Using <b>Loc8.LOCATION_MANAGER</b> TAG  Android default <b>Location Manager</b>.


```
  Loc8 loc8 = Loc8.getInstance(mcontext, Loc8.LOCATION_MANAGER);
        loc8.getLocation(new LocationCallback() {
            @Override
            public void onError(String error) {
               }
            @Override
            public void onSuccess(Location location) {
              }
        });

```
#### Check if location is mocked


```
 Loc8.isLocationFromMockProvider(mcontext,mLocation)
```
#### Check if Mock location app aviliable in Phone
```
 Loc8.areThereMockPermissionApps(mcontext)
```

# Installation

#### Add it to your build.gradle with:
```gradle
allprojects {
    repositories {
        maven { url "https://jitpack.io" }
    }
}
```
and:

```gradle
dependencies {
	        compile 'com.github.RedCarpetUp:Loc8:0.2'
}
```
## Note

#### Hey, this library is in beta right now so if you face any issues we request you to post an issue and we’ll make sure we solve it asap. Also, if you’re a curious developer, we encourage you to fork and push your changes, we’d love to have you on board as a contributor!


# License

```
     Copyright [2017] [Redcarpetup]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

```




