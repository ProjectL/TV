
#Project L

##TV - Objective Display Object
===

Project L TV is a Shared Display of Content.

   We all have these little, and even big powerful devices in our pockets. Our own personal worlds. In Project L, your phone or tablet is an interface to the greater world around you.

   It is what is it, but we as humans are becoming more comfortable initiating interaction with one another through a device.

   So this object is being designed to help bring us closer by having an always available interactive shared world to post and share to, an objective view of the reality around us, that we can contribute to using our subjective handheld devices.

   There is a strong belief in teamXNA that the very moment, the time & space that you stand amongst others is the most unique one available. Early morning @ the coffee shop, in the bank @ lunch time, those moments hold the most valuable connections with others who also happen to be sharing the same time and same place with you.

   But as children growing up we are taught not to talk to strangers, and as adults we teach our kids those same value. But rightfully so, in this terror filled world. Through spontaneous protected safe in person collaboration we can minimize that terror, and establish a better sense of feeling around others, no matter how they look and who they are.

   Even greater, is the change possible in environments we spend lots of our time in. To be able to spontaneously collaborate and further a culture in that home, work or school environment, just by being able to post a msg on a screen, or post an image on a display, has awesomeness written all over it.


####JSON representation of a L TV:

```json
{
"tv": {
        "tvid": "",
        "androidid": "",
        "udid": "",
        "queueid": "",
        "localeid": "",
        "device": [
                {
                        "ble": "",
                        "wifi": "",
                        "cellular": "",
                        "ethernet": "",
                        "isFast": ""
                }
                ],
        "channels": [
                {"channelid": "",
                 "channelname": ""
                }
        ],
        "scene_count": "",
        "tvgeo": {
            "lat": "",
            "long": ""
                },
        "containerid": ""
     }
}
```
TODO
------------
* Add visuals
* Focus on what behaviors the TV has. What can it Do?


Repository Goals
------------
* create an example TV in code
* Learn and experiment through thought


Contribution
------------

Use [Github issues](https://github.com/projectL/Tv/issues) for requests.


Inspirations
------------
meetups, family bbqs, being in a dormitory, being confined
