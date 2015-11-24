# Pushover
Available since [[r3203|http://flexget.com/changeset/3203]].

## Overview
This plugin provides the ability to send flexget notifications via the cross-platform notification system called [[Pushover|http://pushover.net/]].

> Pushover is a platform for sending and receiving push notifications.  On the server end, it provides an HTTP API for queueing messages to deliver to clients. On the client end, the iOS and Android clients receive those push notifications, show them to the user, and store them for offline viewing.  Due to the design of the systems, it does not store messages on the servers once they have been reliably received by the device client.

## Configuration
### Simple
The simplest Pushover plugin configuration requires only the user key (`userkey`) and API key (`apikey`).  This will broadcast the notification to all registered devices.
#### Example

    pushover:
      userkey: o23ywmAaaxT[[Yxn00jY2]]J[[AwQ2Ee]]YXGt
      apikey: nqC2fSOLCEyHH[[JcnusQtw4wqG2WbWf]]


### Advanced
More advanced configuration provides the ability to:
* target a specific device (`device`)
* override the notification message title (`title`)
* override the notification message body (`message`)
* override the notification priority (`priority`)
* override the URL sent in the notification (`url`)
* override the default sound (`sound`)
* use multiple userkeys with a list for (`userkey`)

 device::
  (string) device name as specified in the Pushover configuration
 title::
  (string) accepts Jinja2 tags
 message::
  (string) accepts Jinja2 tags
 priority::
  (int) -1 # low, 0 default, 1 = high, accepts Jinja2 tags
 url::
  (url) accepts Jinja2 tags

#### Example

    pushover:
      userkey: 
        - o23ywmAaaxT[[Yxn00jY2]]J[[AwQ2Ee]]YXGt    
        - 0ydna[[F3023jKadfkja9fjdkjaXfdfsay]]SGa
      apikey: nqC2fSOLCEyHH[[JcnusQtw4wqG2WbWf]]
      device: mobile
      title: Downloading {{series_name}}
      message: Episode {{series_id}}
      priority: 1
      url: http://server.example.com/path/to/downloader/ui
      sound: incoming

