# Require field

This plugin will reject any [[entries] that do not have the specified [wiki:Entry#Knownfields fields|Entry]]. Also rejects if specified field is present, but is an empty string.
**Example:**

This example does the same thing as the [[imdb_required] plugin. (As long as [wiki:Plugins/imdb_lookup imdb_lookup|Plugins/imdb_required]] is also enabled on the task.)

    require_field: imdb_url

**Example:**

This example will reject entries that do not have parsed series information.

    require_field:
      - series_name
      - series_season
      - series_episode

