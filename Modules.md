# Plugins (for 0.9)

```html
<h1 style="text-align: left; color: red">Note: 0.9.x is no longer maintained</h1>
```

[[View latest plugins instead|Plugins]]

Due messy wiki (which is being re-organized) many plugin documentations are not available OR they have 1.0 specific features. You can use `flexget --doc <plugin>` to view FlexGet builtin documentation.

## Inputs

Produce [[entries|Entry]] from external source.

||**Keyword*'||'*Description**||
||[[rss|InputRSS]]||Parse RSS-feed.||
||[[html|InputHtml]]||Parse any HTML-page.||
||[[csv|InputCSV]]||Parse any CSV-file from URL.||
||[[text|InputText]]||Parse any text data from URL.||
||[[rlslog]||Parse [http://rlslog.net|Input[[RlsLog]]]].||
||[[scenereleases]||Parse [http://scenereleases.info|Input[[SceneReleases]]]].||
||[[tvt]||Parse [http://tvtorrents.com|InputTVTorrents]].||

## Filters

Filter, Reject or Accept feeds [[entries|Entry]] based on given rules. Single feed may have any number of filters.

||**Keyword*'||'*Description**||
||[[regexp|FilterRegexp]]||Reject, Accept and Filter content by using regular expression.||
||[[imdb|FilterImdb]]||Accept movie entries based on imdb details.||
||[[series|FilterSeries]]||Accept TV-serie episodes. Quality and episode number aware.||
||[[exists|FilterExists]]||Reject entries based on existing files in filesystem.||
||[[limit_new|Filter[[LimitNew]]]]||Allow only given number of entries to pass per execution.||
||[[seen_movies|Filter[[SeenMovies]]]]||Rejects already downloaded movies (detected by imdb-link).||
||[[seen]||Reject already downloaded entries. [wiki:Builtin|FilterSeen]]||
||[[torrent_size|Filter[[TorrentSize]]]]||Reject torrents that do not meet size requirements.||
||[[patterns]||[wiki:[[ToBeRemoved]] Deprecated|FilterPatterns]]. Accept entries based on regexp. Non-matching entries are filtered.||
||[[accept]||[wiki:[[ToBeRemoved]] Deprecated|FilterUnconditionally]]. Accept entries based on regexp.||
||[[ignore]||[wiki:[[ToBeRemoved]] Deprecated|FilterIgnore]]. Reject entries based on regexp.||

If you plan to use multiple filters per feed, you should look [[filter operations|FilterOperations]] to understand how filters co-operate.

## Outputs

Execute operation(s) to entries that pass trough filter(s).

||**Keyword*'||'*Description**||
||[[download|OutputDownload]]||Download passed entries into given path.||
||[[make_rss|OutputRSS]]||Generate RSS-feed file from passed entries.||
||[[statistics|OutputStatistics]]||Output statistics about downloaded entries.||
||[[subtitles]||Download subtitles for movies from [http://opensubtitles.com opensubtitles.com|OutputSubtitles]].||
||[[exec|OutputExec]]||Execute command for passed entries.||
||[[email|OutputEmail]]||Send email when new content is passed.||

## Modify / Other

||**Keyword*'||'*Description**||
||[[interval|ModuleInterval]]||Maintain minimum poll interval for a feed.||
||[[cookies|ModuleCookies]]||Enable cookies for all HTTP-requests.||
||[[headers|ModuleHeaders]]||Modify HTTP headers.||
||[[extension|ModifyExtension]]||Force a file extension.||
||[[remove_trackers|Modify[[RemoveTrackers]]]]||Remove trackers from a torrent.||
||[[cli_config|Module[[CliConfig]]]]||Allow using values from commandline in YML-configuration file.||
||[[try_regexp|Module[[TryRegexp]]]]||Test how regexps work on feed(s) interactively.||
||[[disable_builtins|Module[[DisableBuiltins]]]]||Disable builtin modules from a feed.||
