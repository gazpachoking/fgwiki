# Plugins

```comment

# just ready for important info

#!html
#<h1 style="text-align: left; color: red">Note: Plugins page is being re-organized so many links are not working</h1>
#<b>This page contains plugins that are available only on bleeding edge.</b> 
```

Plugins provide most of the functionality in FlexGet. Plugins usually create, manipulate or download **[[entries]*' but they can also change how FlexGet operates. Many plugins can use the '*[wiki:Jinja Jinja2 |Entry]]** template system.

Most plugins are enabled by placing a keyword and required settings in a configuration file. All plugins listed below are included in the FlexGet package (with the exception of the third-party plugins section).

## Indentation in examples

All configuration examples are assumed to be placed under a task. So if documentation has this example:


    series:
      - name


In a full configuration, this goes into:


    tasks:
      task_name:
        rss: http://example.com
        series:
          - name


This makes examples more compact and reduces unnecessary boilerplate.


## Inputs


Produce **[[entries|Entry]]** from external source.(XXX macro: "BR")
Most requests are cached so there is no penalty for using the same RSS URL multiple times in the configuration, for example.
**Note:** If you are looking for torrent search plugins, refer to [[Plugins'|'Search]].


### 3rd party sites input

Input plugins designed to retrieve data from 3rd party web-sites, such as IMDB, trakt & etc.
||**Keyword*'||'*Description**||
||[[apple_trailers|Plugins/apple_trailers]]||Get movie trailers from Apple.com||
||[[betaseries_list|Plugins/betaseries_list]]||Use series you follow on www.betaseries.com as an input||
||[[dynamic_imdb |Plugins/dynamic_imdb]]|| `UPDATED` Dynamically produce entries based on an IMDB person, company or character ||
||[[imdb_list|Plugins/imdb_list]]||`UPDATED` Use movies in your IMDb list as an input (eg. watchlist, rating history).||
||[[letterboxd]||Create entries for movies on any public [http://letterboxd.com Letterboxd|Plugins/letterboxd]] list||
||[[myepisodes_list|Plugins/myepisodes_list]]||Create entries from the shows in your myepisodes.com account.||
||[[pogcal]||Produce entries for shows marked on your [http://www.pogdesign.co.uk/cat/ pogdesign calendar|Plugins/pogcal]].||
||[[rlslog]||Parse [http://rlslog.net|Plugins/rlslog]] category.||
||[[rottentomatoes_list]||Use movies from [http://www.rottentomatoes.com Rotten Tomatoes|Plugins/rottentomatoes_list]] lists.||
||[[sceper]||Parse [http://sceper.ws|Plugins/sceper]].||
||[[thetvdb_favorites|Plugins/thetvdb_favorites]]||Produce an entry for all shows you have marked as favorites at http://thetvdb.com.||
||[[trakt_emit|Plugins/trakt_emit]]||Create entries for the latest or the next episode to watch or collect by your trakt.tv activity.||
||[[trakt_list|Plugins/trakt_list]]||Create entries from one of your trakt.tv lists.||
||[[twitterfeed|Plugins/twitterfeed]]||Create entries from a twitter account.||
||[[whatcd]||Produce entries for content on [https://what.cd|Plugins/whatcd]]||

### 3rd party software input

Input plugins designed to retrieve data from 3rd party software, such as Sonarr, couchpotato, deluge & etc.
||**Keyword*'||'*Description**||
||[[couchpotato|Plugins/couchpotato]]||Produce entries from couchpotato wanted list||
||[[from_deluge|Plugins/from_deluge]]||Use torrents loaded in a Deluge daemon as input.||
||[[from_rtorrent|Plugins/rtorrent]]||Use torrents loaded in a rTorrent as input.||
||[[from_transmission|Plugins/from_transmission]]||Use torrents loaded in Transmission as input.||
||[[plex]||Produce entries for shows present in a [http://www.plexapp.com Plex Media Server|Plugins/plex]] section.||
||[[sickbeard|Plugins/sickbeard]]||Produce entries from Sickbeard's show list||
||[[sonarr|Plugins/sonarr]]||Produce entries from Sonarr's show list||
||[[sonarr_emit |Plugins/sonarr_emit]]||Produce entries for missing episodes from Sonarr||

### Internal Input

Input plugins that will generate entries based on preexisting data in FlexGet.
||**Keyword*'||'*Description**||
||[[configure_series|Plugins/configure_series]]||Configures the series plugin with all the shows given by any input plugin (eg. listdir, rss). ||
||[[discover|Plugins/discover]]||Produce entries from search results.||
||[[emit_digest]||Outputs entries which have been collected by the [wiki:Plugins/digest digest|Plugins/emit_digest]] plugin.||
||[[emit_movie_queue]||Emit your [wiki:Plugins/movie_queue movie_queue], useful for example with [wiki:Plugins/discover discover|Plugins/emit_movie_queue]].||
||[[emit_series]||Emit the next episode needed for each series configured in the series plugin. Useful for example with [wiki:Plugins/discover discover|Plugins/emit_series]].||
||[[inputs|Plugins/inputs]]||Configure the same input plugin multiple times in one task.||

### Raw Input

Input plugins that directly parse data from a source based on its type.
||**Keyword*'||'*Description**||
||[[csv|Plugins/csv]]||Parse any CSV-file||
||[[filesystem|Plugins/filesystem]]||Search through a local directory looking for files as a input. ||
||[[html|Plugins/html]]||Parse any HTML-page.||
||[[rss|Plugins/rss]]||Parse RSS-feed.||
||[[sftp_list|Plugins/sftp_list]]||List files from an SFTP server||
||[[tail|Plugins/tail]]||Tail a log file (eg. irc logs)||
||[[text|Plugins/text]]||Parse any text data||
||[[regexp_parse|Plugins/regexp_parse]]||Use regular expressions to parse text from a web resource or file||
||[[ftp_list|Plugins/ftp_list]]||Lists the content of a remote FTP server||

## Filters

Reject or Accept **[[entries|Entry]]** based on given rules. A single task may have any number of filters.(XXX macro: "BR")
If you plan to use multiple filters per task, you should look at **[[filtering operations|Filtering]]** to understand how they work.

### Content based filters

Filters based on the nature of the input content (such as movie, series, series premiere & etc.)
||**Keyword*'||'*Description**||
||[[all_series|Plugins/all_series]]||Accepts any entry that appears to be an episode of a series.||
||[[movie_queue|Plugins/movie_queue]]||Accept movies from movie queue.||
||[[proper_movies|Plugins/proper_movies]]||Keep track of downloaded movies and force re-download proper versions.||
||[[series|Plugins/series]]||Accept TV-series episodes. Quality and episode number aware.||
||[[series_premiere|Plugins/series_premiere]]||Accept any entry that appears to be the first episode of a series.||

### Metadata filters

Filters based on content's metadata such as size and quality
||**Keyword*'||'*Description**||
||[[content_size|Plugins/content_size]]||Reject torrents and nzb's that do not meet size requirements.||
||[[quality|Plugins/quality]]||Reject entries not of the specified quality.||

### FlexGet internal filters

Filters based on preexisting data or operations within FlexGet
||**Keyword*'||'*Description**||
||[[limit_new|Plugins/limit_new]]||Allow only given number of entries to pass per execution.||
||[[only_new|Plugins/only_new]]||Causes all entries that were in the task on the previous run to be rejected at the input phase.||
||[[require_field|Plugins/require_field]]||Reject entries that do not have the specified fields.||
||[[seen_movies|Plugins/seen_movies]]||Rejects already downloaded movies (detected by imdb-link).||
||[[seen]||Reject already downloaded entries. [wiki:Builtin|Plugins/seen]]||
||[[subtitle_queue|Plugins/subtitle_queue]]||Add or accept files to get subtitles for.||

### Torrent specific filters

Filters based specifically for torrents
||**Keyword*'||'*Description**||
||[[content_filter|Plugins/content_filter]]||Reject based on filenames within torrents.||
||[[magnets|Plugins/magnets]]||Rejects entries with only magnet links.||
||[[private_torrents|Plugins/private_torrents]]||Reject private or public torrents.||
||[[seen_info_hash]||Rejects already downloaded torrents (detected by torrent info hash). [wiki:Builtin|Plugins/seen_info_hash]]||
||[[torrent_alive|Plugins/torrent_alive]]||Reject any torrents that do not have an active tracker with seeds.||

### Logical and operational filters

Filters that will accept/reject entries based on logical statements or simple file operations
||**Keyword*'||'*Description**||
||[[accept_all|Plugins/accept_all]]||Accept all entries.||
||[[exists|Plugins/exists]]||Reject entries based on existing files in filesystem.||
||[[exists_series|Plugins/exists_series]]||Reject entries based on existing series in filesystem.||
||[[exists_movie|Plugins/exists_movie]]||Reject entries based on existing movies in filesystem.||
||[[if|Plugins/if]]||Filter based on simple python statements.||
||[[regexp|Plugins/regexp]]||Reject, Accept entries by using regular expression.||

### 3rd party sites filters

Filters based on data retrieved from 3rd party sites
||**Keyword*'||'*Description**||
||[[crossmatch|Plugins/crossmatch]]||Accept/reject based on other inputs (eg. imdb_list watchlist, ratings history).||
||[[imdb|Plugins/imdb]]||Accept movie entries based on imdb details.||
||[[imdb_required|Plugins/imdb_required]]||Reject imdb incompatible entries.||
||[[rottentomatoes|Plugins/rottentomatoes]]||Accept movie entries based on Rotten Tomatoes details.||


## Output

Execute operation(s) on accepted entries.

### 3rd party software output

Send accepted entries to 3rd party software, usually downloaders.
||**Keyword*'||'*Description**||
||[[aria2|Plugins/aria2]]||Pass URIs to be downloaded to a local computer to the aria2 downloader.||
||[[deluge|Plugins/deluge]]||Pass torrents directly to deluge bittorrent client, supporting magnet links.||
||[[nzbget|Plugins/nzbget]]||Download nzbs with nzbget.||
||[[periscope|Plugins/periscope]]||Download subtitles with Periscope.||
||[[pyload|Plugins/pyload]]||http://pyload.org/.||
||[[rtorrent|Plugins/rtorrent]]||Pass torrents directly to rtorrent||
||[[rtorrent_magnet|Plugins/rtorrent_magnet]]||Handles magnet URI's and produces rTorrent compatible torrent files (0.8.9+)||
||[[sabnzbd|Plugins/sabnzbd]]||Download nzbs with SABnzbd.||
||[[subliminal|Plugins/subliminal]]||Download subtitles with Subliminal.||
||[[transmission|Plugins/transmission]]||Pass torrents directly to transmission, supporting magnet links.||
||[[utorrent|Plugins/utorrent]]||Pass torrents directly to uTorrent.||

### 3rd party sites output

Send accepted entries to 3rd party sites, usually for tracking purposes. 
||**Keyword*'||'*Description**||
||[[myepisodes|Plugins/myepisodes]]||Mark accepted episodes as acquired on MyEpisodes.||
||[[thetvdb_add|Plugins/thetvdb_add]]||Add accepted series to user's thetvdb.com favorites.||
||[[thetvdb_remove|Plugins/thetvdb_remove]]||Remove accepted series from user's thetvdb.com favorites.||
||[[pogcal_acquired]||Mark accepted episodes on [http://pogdesign.co.uk/cat pogdesign TV calendar|Plugins/pogcal_acquired]]||
||[[trakt_add|Plugins/trakt_add]]||Add accepted episodes/movies to a list on trakt.tv.||
||[[trakt_remove|Plugins/trakt_remove]]||Remove accepted episodes/movies from a list on trakt.tv.||

### Notifier services output

Send accepted entries to notification services.
||**Keyword*'||'*Description**||
||[[email|Plugins/email]]||Send email when new content is passed.||
||[[prowl|Plugins/prowl]]||Send prowl notifications (iPhone).||
||[[pushover|Plugins/pushover]]||Send Pushover notifications (iPhone and Android).||
||[[rapidpush|Plugins/rapidpush]]||An easy-to-use push notification service. (Android).||
||[[notify_osd|Plugins/notify_osd]]||Send notifications to notify-osd.(linux only. Ubuntu tested)||
||[[notify_xmpp|Plugins/notify_xmpp]]||Send notifications via XMPP.||
||[[notifymyandroid|Plugins/notifymyandroid]]||Send notifications to android.||
||[[pushbullet|Plugins/pushbullet]]||Send Pushbullet notifications (Android/iOS/Windows/Chrome Extension).||
||[[pushalot|Plugins/pushalot]]||Send Pushalot notifications (Windows 8/Windows Phone).||

### FlexGet internal output

Use accepted entries as an input for various FlexGet plugins such as add to movie queue, set series begin & etc.
||**Keyword*'||'*Description**||
||[[digest|Plugins/digest]]||Collects entries from tasks to be combined into another task (usually for notification.)||
||[[movie_queue|Plugins/movie_queue]]||Add movies to movie queue.||
||[[set_series_begin|Plugins/set_series_begin]]||Set the first episode to download for series.||

### File operations output

Perform different file operations using accepted entries.
||**Keyword*'||'*Description**||
||[[copy|Plugins/copy]]||Copy local files.||
||[[decompress|Plugins/decompress]]||Extract Zip and RAR files.||
||[[delete|Plugins/delete]]||Delete local files.||
||[[download|Plugins/download]]||Download passed entries into given path.||
||[[exec|Plugins/exec]]||Executes commands on entries.||
||[[ftp_download]||Download entries retrieved from [wiki:Plugins/ftp_list ftp_list|Plugins/ftp_download]]||
||[[move|Plugins/move]]||Move local files.||
||[[sftp_download|Plugins/sftp_download]]||Download files from an SFTP server||
||[[sftp_upload|Plugins/sftp_upload]]||Upload files to an SFTP server||

### Generators output

Generate custom output using accepted entries
||**Keyword*'||'*Description**||
||[[make_html|Plugins/make_html]]||Generate HTML file from passed entries.||
||[[make_rss|Plugins/make_rss]]||Generate RSS-feed file from passed entries.||
||[[send_telegram|Plugins/send_telegram]]||Send a Telegram message from passed entries.||

## Metadata plugins

Retrieve additional data from 3rd party sites. Used for population of more fields than default or to actively perform data retrieval for specific input types.
These are usually automatic (**[[plugins which provide metainfo (fields) to *'[wiki:Entry|Builtin]'*)]]**.
||**Keyword*'||'*Description**||
||[[imdb_lookup|Plugins/imdb_lookup]]||Enable imdb parsing for imdb fields on-demand.||
||[[rottentomatoes_lookup|Plugins/rottentomatoes_lookup]]||Enable Rotten Tomatoes parsing for Rotten Tomatoes fields on-demand.||
||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Fetch series information from thetvdb.||
||[[tmdb_lookup|Plugins/tmdb_lookup]]||Enable http://www.themoviedb.org/ parsing for tmdb fields on-demand.||
||[[trakt_lookup|Plugins/trakt_lookup]]||Enable Trakt.tv parsing for trakt fields on-demand.||
||[[check_subtitles|Plugins/check_subtitles]]^1||Check subtitles presence for local files.||
^1. Not a builtin, configuration required to enable.^

## Modification plugins

Plugins that can manipulate data and perform various operations.

### Request operations

Perform various operations on request that are being sent and received. 
||**Keyword*'||'*Description**||
||[[cfscraper|Plugins/cfscraper]]||Enables cloudflare scraping in a task.||
||[[cookies|Plugins/cookies]]||Use [[FireFox3]] cookies.||
||[[domain_delay|Plugins/domain_delay]]||Sets a minimum interval between requests to specific domains.||
||[[formlogin|Plugins/formlogin]]||Log in to web site via login form.||
||[[headers|Plugins/headers]]||Modify HTTP headers.||
||[[proxy|Plugins/proxy]]||Use a proxy to access resources.||
||[[remove_trackers|Plugins/remove_trackers]]||Remove trackers from a torrent.||
||[[urlrewrite_search|Plugins/urlrewrite_search]]||Search for download URL from supported sites.||

### File operations

Perform file oriented operations.
||**Keyword*'||'*Description**||
||[[extension|Plugins/extension]]||Force a file extension.||
||[[free_space|Plugins/free_space]]||Abort task when drive space is low.||
||[[path_by_ext|Plugins/path_by_ext]]||Change (download) path based on file-type (extension).||
||[[path_select|Plugins/path_select]]||Select a path based on disk stats||
||[[set|Plugins/set]]||Set 'path' or other info per task. Can be dynamic per entry.||

### Data operations

Manipulate relevant data based on input.
||**Keyword*'||'*Description**||
||[[assume_quality|Plugins/assume_quality]]||Make assumptions about the qualities of releases.||
||[[add_trackers|Plugins/add_trackers]]||Add trackers to torrents.||
||[[manipulate|Plugins/manipulate]]||Allows regexp manipulation for entries.||
||[[parsing|Plugins/parsing]]||Configure another parser for series and movie titles. (can help if IMDB/TMDB/TVDB lookup fails too often)||
||[[pathscrub|Plugins/pathscrub]]||Cleans invalid characters from generated path/file names. (Used by other plugins that generate files.)||
||[[torrent_scrub|Plugins/torrent_scrub]]||Removes non-standard keys like libtorrent resume information from downloads (which prevents the torrent from properly starting in Rtorrent).||
||[[urlrewrite|Plugins/urlrewrite]]||User regexp for URL Rewriting.||

### FlexGet internal operations

Perform various FlexGet operations.
||**Keyword*'||'*Description**||
||[[archive|Plugins/archive]]||Archive all seen entries for searchable database for later retrieval.||
||[[delay|Plugins/delay]]||Adds artificial delay into a task.||
||[[disable|Plugins/disable]]||Disable builtin plugin(s) from a task, or plugins included from a template.||
||[[include|Plugins/include]]||Include configuration from another yaml file.||
||[[interval|Plugins/interval]]||Maintain minimum poll interval for the task.||
||[[manual|Plugins/manual]]||Only run the task when explicitly specified.||
||[[no_entries_ok|Plugins/no_entries_ok]]||Silence warnings about task not producing entries, for tasks where that is normal.||
||[[priority|Plugins/priority]]||Change task execution order.||
||[[plugin_priority|Plugins/plugin_priority]]||Change plugin priorities.||
||[[remember_rejected|Plugins/remember_rejected]]||Remember rejections and reject them in future runs.||
||[[retry_failed]||Save failed entries so they can be retried. [wiki:Builtin|Plugins/retry_failed]]||
||[[secrets|Plugins/secrets]]||Replace specific jinja2 values in config before executing tasks.||
||[[sequence|Plugins/sequence]]||Allows the same plugin to be configured multiple times in a task.||
||[[sleep|Plugins/sleep]]||Causes a pause to occur at a specified point during task execution.||
||[[sort_by|Plugins/sort_by]]||Sort entries in a task.||
||[[template|Plugins/template]]||Provides global configuration and named templates.||
||[[verify_ssl_certificates|Plugins/verify_ssl_certificates]]||Can turn off SSL certificate verification on a task.||

### 3rd party software

Perform operations on 3rd part software.
||**Keyword*'||'*Description**||
||[[clean_transmission|Plugins/clean_transmission]]||Clean Transmission queue.||
||[[plugin_rutracker|Plugins/plugin_rutracker]]||Supports downloading torrents from rutracker.||

## Search

||[[search_rss|Plugins/search_rss]]||Search with parametrized rss feed.||

## Daemon

These plugins are specifically for when FlexGet is being used in daemon mode. They differ from the other plugins documented here, in that they should be configured at the root of your config. Not inside any tasks or templates.

||[[scheduler|Plugins/Daemon/scheduler]]||Executes tasks with a given interval or schedule while daemon is running.||

## Command line plugins for `execute` command

||[[--cli-config|Plugins/--cli-config]]||Allow using values from commandline in YML-configuration file.||
||[[--dump|Plugins/--dump]]||Display all entries after task execution.||
||[[--tasks|Plugins/--tasks]]||Executes only the specified task(s)||
||[[--inject|Plugins/--inject]]||Injects custom entry into task(s).||
||[[--try-regexp|Plugins/try_regexp]]||Test how regexps work on task(s) interactively.||

## Third-party plugin

Plugins can be installed by simply placing them in `~/.flexget/plugins/`

||[[my_movie_filter|https://github.com/atlanta800/dotfiles/blob/master/flexget/plugins/my_movie_filter.py]]||An extremely specific custom movie filter by atlanta800.||
||[[jdownloader|http://flexget.com/ticket/1435]]||jDownloader output - perhaps included in the core package sooner or later.||
