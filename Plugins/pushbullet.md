# Pushbullet
## Overview
This plugin provides the ability to send flexget notifications via the notification system called [[Pushbullet|https://www.pushbullet.com/]].

Pushbullet is also available as native apps on Android, iOS, Windows and also as Chrome extension.

> Pushbullet shows you all of your phone's notifications right on your computer so you never miss a notification again!
> Pushbullet also lets you send push notifications to yourself and to your friends!
> Why send push notifications with Pushbullet? Because it's the easiest and fastest way to send almost anything to your phone or to your friends.
> What can you push with Pushbullet? Send links, pictures, files, lists, notes, and more right into your phone's notification tray, to your computer, or to a friend, really fast.

== Configuration Options==

    pushbullet:
      apikey: <API_KEY> (can be a list of API keys)
      [[<DEVICE_IDEN> (can also be a list of device idens, or don't specify any idens to send to all devices)|device:]]
      [[<EMAIL_ADDRESS> (can also be a list of user email addresses)|email:]]
      [[<CHANNEL_TAG> (can also be a list of channel tags)|channel:]]
      [[<MESSAGE_TITLE>|title:]] (default: "{{task}} - Download started" -- accepts Jinja2)
      [[<MESSAGE_BODY>|body:]] (default: "{{series_name}} {{series_id}}" -- accepts Jinja2)
      [[<LINK_URL>|url:]] (default: empty -- accepts Jinja2)


DEVICE_IDEN can by found by running: 

    curl -u <API_KEY>: https://api.pushbullet.com/api/devices


DEVICE_IDEN can also be a list if you would like to send the same notification to multiple devices. Alternatively if you do not specify any DEVICE_IDENs, the push will be delivered to all the devices associated with your API_KEY.

## Example

An example that sends to two [[PushBullet]] accounts, with a heavily customised title and body messages.


        pushbullet:
          apikey:
            - xxxxxxx1
            - xxxxxxx2
          title: >
            {% if series_name is defined %}{{tvdb_series_name|d(series_name)}} - {{series_id}}
            {% elif imdb_name is defined %}{{imdb_name}} ({{imdb_year}})
            {% else %}{{title}}
            {% endif %}
          body: >
            {% if series_name is defined %}{{tvdb_series_name|d(series_name)}} - {{series_id}} - {{tvdb_ep_name|d('')}}{% if quality is defined %} ({{quality}}){% endif %}
            {% elif imdb_name is defined %}{{imdb_name}} ({{imdb_year}}){% if quality is defined %} ({{quality}}){% endif %}
            {% else %}{{title}}{% if quality is defined %} ({{quality}}){% endif %}
            {% endif %}

