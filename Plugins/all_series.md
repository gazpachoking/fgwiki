# All Series

Automatically configures the [[series|Plugins/series]] plugin for all series that appear in the feed.

Plugin expects the title format to start with the series name followed by the episode numbering. Use the [[manipulate] plugin to modify the entry title to match this format, if necessary. Since it's very hard to guess series names you're much more likely to get significantly more robust matching (and thus downloading) with configuring [wiki:Plugins/series series|Plugins/manipulate]] plugin with **explicit** series names. You can also mix and match all different configuration methods.
**Examples:**

Turns on the plugin for a task.


    all_series: yes


## Series Settings

Behind the scenes, all_series just configures the [[series] plugin with all the series it sees in the feed.*** You can use any of the [wiki:Plugins/series#Settings settings|Plugins/series]] of the series plugin for all_series.
** Example **


    all_series:
      path: /media/TV
      quality: 720p hdtv
      propers: no

