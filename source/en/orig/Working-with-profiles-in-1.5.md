Since version 1.5 the logic of using profiles changed.

Up to version 1.46 once you change profile the changes are immediately applied. 

AAPS may still work this old fashioned way until you create first "Profile switch" event with zero duration (explained later). By doing this AAPS starts tracking history of profiles and every new profile change requires another "Profile switch" even when you change content of the profile in NS. Updated profile is pushed to AAPS immediately but you need to switch the same profile again (in NS or AAPS) to start using these changes.

Internaly AAPS creates snapshot of profile with start date and duration and is using it within selected period. Duration of zero means infinite. Such profile is valid until new "Profile switch".

If you use "Profile switch" with duration profile is switched back to previous valid "Profile switch"

If you use local AAPS profiles (CPP, Simple, Local) you have to press button there to apply these changes (it creates proper "Profile switch" event).

This mechanism allows much precise calculations to the past and track profile changes.

In closed loop mode is recommended to turn on automatic update of profile in pump (in settings).