# strava_flutter

Dart/flutter package to use Strava API v3

Follow the "new" Authentication process

https://developers.strava.com/docs/authentication/



## API currently supported:

### Authentication
- authorize
- deauthorize

### Athlete related APIs
- getLoggedInAthlete
- updateLoggedInAthlete (scope profile:write)
- getLoggedInAthleteActivities (not limited)
- getLoggedInAthleteZones
- getGearById
- getStats 
### Club related APIs
- getClubById
- getClubActivitiesById 
- getClubMembersById 
### Race related APIs
- getRunningRaces
- getRunningRaceById
### Activity related APIs
- createActivity
- uploadActivity (includes getUploadById) 
Tested on TCX and GPX
To generate TCX you can use the following package
https://pub.dev/packages/rw_tcx

### Segments related APIs
- getSegmentById
- getLoggedInAthleteStarredSegments
- getLeaderboardBySegmentId (not limited)
- starSegment


## How to install
Check on pub.dev/packages to see how to install this package

https://pub.dev/packages/strava_flutter#-installing-tab-

### Additional steps when running on Android Pie 9.0 (API level 28)

The webview returned by the auth process may throw `net::ERR_CLEARTEXT_NOT_PERMITTED`. In this case add `android:usersCleartextTraffic="true"` to `the AndroidManifest.xml` like below:

```
<application
    ....
    android:usesCleartextTraffic="true"
    ....>
 ```


## How to use it

1 -Get the client secret in your Strava settings related to your app https://www.strava.com/settings/api with "Authorization Callback Domain" set to "127.0.0.1"

2  - Create a file secret.dart and put in this file:
final String secret = "[Your client secret]";
final String clientId = "[Your appID]";

3 - import 'secret.dart' when you need secret and clientId in Strava API

4 - To see debug info in Strava API, set isInDebug to true in Strava() init

5 - Please check examples.dart for the moment

https://github.com/BirdyF/strava_flutter/blob/master/example/lib/main.dart

https://github.com/BirdyF/strava_flutter/blob/master/example/lib/examples.dart


If you have any problem or need an API not yet implemented please post a new issue


## Tested on:
- Android 4.4.2 , 4.4.23, 8.0.0, 9.0
- iOS 12.1, 12.1.2, 12.1.4


## Contributors welcome!
If you spot a problem/bug or if you consider that the code could be better please post an issue.
I am not planning to implement all the Strava APIs, because I dont need all of them in my dev.
But let me know if you need some APIs that are not in the current list and I will add it.
Alternatively, you can easily implement additional API and I will add it to strava_futter.


## Thanks 

Thanks to Joe Birch, I used his code to better understand Oauth process
https://github.com/hitherejoe/FlutterOAuth

And Javier for https://javiercbk.github.io/json_to_dart/


## License:
strava_flutter is provided under a MIT License. Copyright (c) 2019 Patrick FINKELSTEIN
