{{{
#!html
<h1 style="text-align: left; color: red">Note:</h1>
<b>This page contains plugins that are available only on bleeding edge.</b> 
}}}
For stable release, please look instead [wiki:Modules here].

= Plugins =

Formerly known as modules. Please see [wiki:MigrateTo10 migrate guide] if you have previously used !FlexGet.

Plugins provide most of the functionality in !FlexGet. Plugins usually create, manipulate or download [wiki:Entry entries] but they can as well change how !FlexGet operates.

Plugin is enabled by placing a keyword and required settings in a configuration file. Example [wiki:InputRSS rss-module] would be used by placing following line under feed. See [wiki:Configuration configuration] if you are not familiar with the structure.

{{{
rss: http://some.site.com/some_feed.rss
}}}

== Indentation in examples ==

All configuration examples are assumed to be placed under a feed. So if documentation has example:

{{{
series:
  - name
}}}

In full configuration this goes into:

{{{
feeds:
  feed_name:
    rss: http://example.com
    series:
      - name
}}}

This makes examples more compact and reduces unnecessary boilerplate.

== Inputs ==

Produce [wiki:Entry entries] from external source.

||'''Keyword'''||'''Description'''||
||[wiki:InputRSS rss]||Parse RSS-feed.||
||[wiki:InputHtml html]||Parse any HTML-page.||
||[wiki:InputCSV csv]||Parse any CSV-file||
||[wiki:InputText text]||Parse any text data||
||[wiki:InputDirectories directories]||'''{{{NEW}}}''' Use any local directory listing as a input.||
||[wiki:InputRlsLog rlslog]||Parse [http://rlslog.net] category.||
||[wiki:InputSceneReleases scenereleases]||Parse [http://scenereleases.info].||
||[wiki:InputTVTorrents tvt]||Parse [http://tvtorrents.com].||

== Filters ==

Reject or Accept [wiki:Entry entries] based on given rules. Single feed may have any number of filters.

||'''Keyword'''||'''Description'''||
||[wiki:FilterAcceptAll accept_all]||'''{{{NEW}}}'''  Accept all entries.||
||[wiki:FilterRegexp10 regexp]||Reject, Accept entries by using regular expression.||
||[wiki:FilterImdb imdb]||Accept movie entries based on imdb details.||
||[wiki:FilterImdbRated imdb_rated]||'''{{{NEW}}}''' Reject already voted entries.||
||[wiki:FilterImdbRequired imdb_required]||'''{{{NEW}}}''' Reject imdb incompatible entries.||
||[wiki:FilterSeries10 series]||'''{{{Upgraded}}}''' Accept TV-serie episodes. Quality and episode number aware.||
||[wiki:FilterExists10 exists]||Reject entries based on existing files in filesystem.||
||[wiki:FilterExistsSeries exists_series]||'''{{{New}}}''' Reject entries based on existing series in filesystem.||
||[wiki:FilterLimitNew limit_new]||Allow only given number of entries to pass per execution.||
||[wiki:FilterSeenMovies seen_movies]||Rejects already downloaded movies (detected by imdb-link).||
||[wiki:FilterSeen10 seen]||'''{{{Upgraded}}}''' Reject already downloaded entries. [wiki:Builtin]||
||[wiki:FilterTorrentSize torrent_size]||Reject torrents that do not meet size requirements.||

If you plan to use multiple filters per feed, you should look [wiki:FilterOperations filter operations] to understand how filters co-operate.

== Outputs ==

Execute operation(s) to accepted entries.

||'''Keyword'''||'''Description'''||
||[wiki:OutputDownload download]||Download passed entries into given path.||
||[wiki:OutputRSS make_rss]||Generate RSS-feed file from passed entries.||
||[wiki:OutputStatistics statistics]||Output statistics about downloaded entries.||
||[wiki:OutputSubtitles subtitles]||Download subtitles for movies from [http://opensubtitles.com opensubtitles.com].||
||[wiki:OutputExec exec]||Execute command for passed entries.||
||[wiki:OutputEmail email]||Send email when new content is passed.||
||[wiki:OutputDeluge deluge]||'''{{{NEW}}}'''  Pass torrents directly to deluge bittorrent client.||
||[wiki:OutputSABnzbs sabnzbs]||'''{{{NEW}}}'''  Download nzbs via SABnzbd.||

== Modify / Other ==

||'''Keyword'''||'''Description'''||
||[wiki:ModuleImdbLookup imdb_lookup]||'''{{{NEW}}}'''  Tries to perform imdb lookup for all entries.||
||[wiki:ModuleSearch search]||'''{{{NEW}}}'''  Search for download URL from supported sites.||
||[wiki:ModulePathByExt path_by_ext]||'''{{{NEW}}}'''  Change (download) path based on file-type (extension).||
||[wiki:ModulePreset preset]||'''{{{NEW}}}'''  Provides global configuration and named presets.||
||[wiki:ModuleCookies10 cookies]||'''{{{UPGRADED}}}''' Use !FireFox3 cookies.||
||[wiki:ModuleInterval interval]||Maintain minimum poll interval for a feed.||
||[wiki:ModuleHeaders headers]||Modify HTTP headers.||
||[wiki:ModifyExtension extension]||Force a file extension.||
||[wiki:ResolveRegexp regexp_resolve]||Easy download URL rewriting.||
||[wiki:ModifyRemoveTrackers remove_trackers]||Remove trackers from a torrent.||
||[wiki:ModuleCliConfig cli_config]||Allow using values from commandline in YML-configuration file.||
||[wiki:ModuleTryRegexp try_regexp]||Test how regexps work on feed(s) interactively.||
||[wiki:ModuleDisableBuiltins disable_builtins]||Disable builtin modules from a feed.||
||[wiki:ModuleFormLogin formlogin]||'''{{{NEW}}}'''  Log in via form.||
||[wiki:ModifySet set]||'''{{{NEW}}}'''  Set 'path' or other info per feed.||
||[wiki:ModuleManipulate manipulate]||'''{{{NEW}}}'''  Allows regexp manipulation for entries.||
||[wiki:ModuleSort sort]||'''{{{NEW}}}'''  Sort entries.||