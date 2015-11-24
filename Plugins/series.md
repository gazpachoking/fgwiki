# Series

Intelligent filter for TV-series.

## Features

* Episode history aware, no duplicate downloads
* Plenty of [[quality|Plugins/series/quality]] options
* [[Timeframe|Plugins/series/timeframe]], get best quality in given timeframe
* Episode [[tracking|Plugins/series/tracking]] (for season, episode).
* [[Proper & Repack|Plugins/series/propers]] aware
* Specials aware (grabs episodes with the series title and the word 'special')
* Tries to ignore season packs, you can use [[content_size|Plugins/content_size]] for extra insurance against them.
* Supports double episodes. i.e. [[S01E01]]-E02
* [[Series searching support] (via [wiki:Plugins/discover discover] and [wiki:Plugins/emit_series emit_series|Cookbook/Series/Search]] plugins)
**Simple configuration:**


    series:
      - some series
      - another series


If `some series` and `another series` have understandable episode
numbering any given episode is downloaded only once. FlexGet should support all known episode numbering schemes without any configuration, including dates.

So if we get same episode twice:

* Some.Series.[[S2E10]].720p.x264-FlexGet
* Some.Series.[[S2E10]].HR.x264-FooBar

Only one of them is downloaded, with default configuration best quality is chosen.

## Related plugins

These plugins are complementary to the series plugin.

* [[all_series|Plugins/all_series]] - Grab all series in the task
* [[import_series|Plugins/import_series]] - Automatically configures series by using another input, some examples:
   * [[thetvdb_favorites] - [http://thetvdb.com TheTVDB.com|Plugins/thetvdb_favorites]] favorites
   * [[trakt_list] - [http://trakt.tv Trakt.tv|Plugins/trakt_list]] lists
   * [[filesystem|Plugins/filesystem]] - You local directory listing
* [[series_premiere|Plugins/series_premiere]] - Download all premieres

## Settings

The series plugin supports a number of settings to customize it's behavior. Though the examples show the settings being applied to a single series, they can all be applied to a group of series as well.

[[How to configure settings per series|Plugins/series/per_series_settings]](XXX macro: "BR")
[[How to configure settings with groups|Plugins/series/per_group_settings]]

||**Option*'||'*Description**||
||[[alternate_name|Plugins/series/alternate_name]]||Define other names which this show is also released as.||
||[[assume_special|Plugins/series/assume_special]]||Assume any entry with no series numbering detected is a special and treat it accordingly.||
||[[begin|Plugins/series/begin]]||Manually specify first episode to start series on.||
||[[ep_regexp|Plugins/series/regexps#Episodenumberingmatching]]||Manually specify regexp(s) that matches to episode, season numbering.||
||[[exact|Plugins/series/exact]]||Configure exact matching behavior. Needed for series which have similar named series. Uses 'auto' mode as default.||
||[[from_group|Plugins/series/from_group]]||Accept series only from given groups.||
||[[id_regexp|Plugins/series/regexps#Episodenumberingmatching]]||Manually specify regexp(s) that matches to series identifier (numbering).||
||[[identified_by|Plugins/series/identified_by]]||Configure how episode numbering is detected. Uses 'auto' mode as default.||
||[[name_regexp|Plugins/series/regexps]]||Manually specify regexp(s) that matches to series name.||
||[[parse_only|Plugins/series/parse_only]]||Series plugin will not accept or reject any entries, merely fill in all metadata fields.||
||[[path|Plugins/series/path]]||Set *path* field for this series.||
||[[prefer_specials|Plugins/series/prefer_specials]]||Flag entries matching both special and a normal ID type as specials.||
||[[propers|Plugins/series/propers]]||Configure how propers are handled.||
||[[qualities|Plugins/series/qualities]]||Download all listed qualities when they become available.||
||[[quality|Plugins/series/quality]]||Required quality.||
||[[set]||Use [wiki:Plugins/set set|Plugins/series/set]] plugin to set any fields for this series.||
||[[special_ids|Plugins/series/special_ids]]||Defines other IDs which will cause entries to be flagged as specials.||
||[[specials|Plugins/series/specials]]||Turn off specials support for series. (on by default)||
||[[target|Plugins/series/timeframe]]||The target quality that should be downloaded without waiting for `timeframe` to complete.||
||[[timeframe|Plugins/series/timeframe]]||Wait given amount of time for specified quality to become available, after that fall back to best so far.||
||[[tracking|Plugins/series/tracking]]||Turn latest episode tracking off, or put into backfill mode.||
||[[upgrade|Plugins/series/upgrade]]||Keeps getting the better qualities as they become available.||


## Notes

* If the series appears in task(s) with slightly different naming conventions and spinoffs like FooBar and FooBar US read [[this guide|Plugins/series/closematch]]. 
* FlexGet respects *propers* which means that the same episode will be downloaded twice if the second one contains words such as `proper`, `repack`, `rerip`, or `real`.
* If series name is written in multiple different ways, don't add them as separate series. This will confuse episode tracking. 
* Check [[series cookbook|Cookbook/Series]] for more complete examples and advanced uses.

## `series` Commandline Arguments

The series plugin has several features available at the command line via the `flexget series` command:

### list

Display series summary. `flexget series list`

### show

Displays the releases for a given show that the series plugin has seen. `flexget series show <name>`

### forget

Delete episodes from database or whole series completely.

To delete single episode, use:

`flexget series forget <name> <id>`

To delete whole series, use:

`flexget series forget <name>`

### begin

Sets the first episode of a show that the series plugin should look for. `flexget series begin <name> <id>`

## `execute` Commandline Arguments

There are also options to the `flexget execute` command which affect the series plugin:

### --disable-tracking

If episode tracking is causing problems downloading latest episode due large gap in the series history, you can use this option to disable advancement enforcement temporarily. If the latest episode that [[FlexGet]] should download is in the feed this argument with `--disable-cache` is usually enough. If the episode is not anymore in the feed you can feed the task imaginary episode via `--inject` and `--learn`. Example:


    flexget execute --inject "Pioneer.One.[[S01E05]].For.[[FlexGet]]" --learn --disable-tracking --tasks NAME


### --stop-waiting

Stops timeframe for given name, thus downloading any episode that is currently pending in the timeframe.
