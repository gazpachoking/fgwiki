# Deluge labels based on series name
**NOTE:** As of r1840 this recipe is not needed as the [[deluge] plugin will replace any invalid characters in the label name with '_' automatically. Also, the [wiki:Plugins/set set|Plugins/deluge]] plugin can now be used to make this sort of replacement much easier.

Deluge does not support spaces in label names, so this has to be worked around in order to have automatic labels based on series names. This can be accomplished by using the [[manipulate] plugin to create the label from series name with spaces replaced by underscores. We also need to use [wiki:Plugins/plugin_priority plugin_priority] to make the manipulate plugin run after [wiki:Plugins/series series], so that series has a chance to populate the [wiki:Entry#Knownfields series_name field|Plugins/manipulate]].

    feeds:
      tv:
        rss: http://feed.com/feed
        series:
          - Series One
          - Series Two
        manipulate:
          - label:
              from: series_name
              replace:
                regexp: ' '
                format: '_'
        plugin_priority:
          manipulate: 0
        deluge: yes

