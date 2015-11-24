# Entry

Entry represents a single item created by input(s), usually a downloadable content.
It contains all the information necessary for [[plugins] to perform their job (usually some [wiki:[[FilterOperations]] operation|Plugins]] on the entry).

For example, the [[regexp|Plugins/regexp]] plugin checks whether the given regular expression matches the entry's **title*' or '*url** and acts accordingly.
**Example of an entry:**

These are mandatory fields

||**Name*'||'*Value**||
||title||Some.Awesome.Series.[[S01E01]].XviD-Foo||
||url||!http://site.com/download/Some.Awesome.Series.[[S01E01]].XviD-Foo.torrent||

## Known fields

Entry *may'' have any of these fields, but is not ''guaranteed* to have any of them. It may have other fields as well depending on configuration. Use `--dump` option to see your task content.

||**Name*'||'''Created by'''||'*Description**||
||path||multiple plugins||Path where this entry content should be saved||
||description||[[rss|Plugins/rss]]||Item description||
||rss_pubdate||[[rss|Plugins/rss]]||Date the RSS item was published||
||task||metainfo_task||Task name which this entry belongs to||
||quality||metainfo_quality, [[series|Plugins/series]]||Detected quality, ie. `720p`||
||quality_req||[[couchpotato]||A quality requirement string, can hold several qualities. Used by [wiki:Plugins/movie_queue movie_queue|Plugins/couchpotato]]||
||series_name||[[series|Plugins/series]], metainfo_series||Series name||
||series_season||[[series|Plugins/series]], metainfo_series||Series season||
||series_episode||[[series|Plugins/series]], metainfo_series||Series episode||
||series_id||[[series|Plugins/series]]||Series episode identifier, ie. `[[S01E02]]` or `2009-12-1`||
||series_date||[[series|Plugins/series]]||The date of the episode. (only available for date based series)||
||proper||[[series|Plugins/series]]||Whether this entry is a proper or repack release||
||imdb_url||[[imdb_lookup|Plugins/imdb_lookup]]+others||Imdb url||
||imdb_id||[[imdb_lookup|Plugins/imdb_lookup]]*||Imdb identifier||
||imdb_name||[[imdb_lookup|Plugins/imdb_lookup]]*||Imdb name||
||imdb_original_name||[[imdb_lookup|Plugins/imdb_lookup]]*||Imdb original name||
||imdb_year||[[imdb_lookup|Plugins/imdb_lookup]]*||Imdb year||
||imdb_score||[[imdb_lookup|Plugins/imdb_lookup]]*||Imdb score||
||imdb_votes||[[imdb_lookup|Plugins/imdb_lookup]]*||Imdb votes||
||imdb_genres||[[imdb_lookup|Plugins/imdb_lookup]]*||List of imdb genres||
||imdb_languages||[[imdb_lookup|Plugins/imdb_lookup]]*||List of imdb languages||
||imdb_photo||[[imdb_lookup|Plugins/imdb_lookup]]*||Url for photo (hotlinking prevented)||
||imdb_plot_outline||[[imdb_lookup|Plugins/imdb_lookup]]*||Plot outline||
||imdb_actors||[[imdb_lookup|Plugins/imdb_lookup]]*||Actors dictionary (key: imdbid, value: name)||
||imdb_directors||[[imdb_lookup|Plugins/imdb_lookup]]*||Directors dictionary (imdbid, name)||
||movie_name||[[imdb_lookup|Plugins/imdb_lookup]]*||Movie title||
||movie_year||[[imdb_lookup|Plugins/imdb_lookup]]*||Movie release year||
||output||[[download|Plugins/download]]||Downloaded file||
||torrent||modify_torrent||When entry is a torrent this contains [[Torrent class|TorrentObject]]||
||data||[[download|Plugins/download]]||Internal. Binary content.||
||content_size||[[content_size|Plugins/content_size]]||Parsed size of torrents or NZBs.||
||location||[[filesystem|Plugins/filesystem]]||The local filename of the entry.||
||timestamp||[[filesystem|Plugins/filesystem]]||The local file update time of the entry.||
||subtitles||[[check_subtitles|Plugins/check_subtitles]]||A list of languages about subtitles founds on disk (local files only)||
||plex_server||[[plex|Plugins/plex]]||If set, PMS hostname. Otherwise PMS IP.||
||plex_server_ip||[[plex|Plugins/plex]]||PMS IP.||
||plex_port||[[plex|Plugins/plex]]||PMS port.||
||plex_section||[[plex|Plugins/plex]]||Section number.||
||plex_section_name||[[plex|Plugins/plex]]||Section name.||
||plex_path||[[plex|Plugins/plex]]||Entry path on PMS.||
||plex_duration||[[plex|Plugins/plex]]||Entry length in seconds.||
||plex_thumb||[[plex|Plugins/plex]]||Episode thumbnail, series only.||
||plex_art||[[plex|Plugins/plex]]||Series or movie art as configured in PMS||
||plex_cover||[[plex|Plugins/plex]]||Series cover for series, movie cover for movies.||
||plex_season_cover||[[plex|Plugins/plex]]||Season cover, series only. If used in movies, movie cover will be set.||
||plex_title||[[plex|Plugins/plex]]||Episode name as indexed on PMS.||
||plex_summary||[[plex|Plugins/plex]]||Entry summary.||
||plex_status||[[plex|Plugins/plex]]||Entry status: seen, inprogress or unwatched.||
||plex_url||[[plex|Plugins/plex]]||Original plex url.||
||tvdb_series_name||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series name provided by thetvdb||
||tvdb_rating||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series rating||
||tvdb_status||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series status(Continuing or Ended)||
||tvdb_runtime||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series runtime in minutes)||
||tvdb_first_air_date||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series premier date||
||tvdb_air_time||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series air time||
||tvdb_content_rating||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series content ration||
||tvdb_genres||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series genres||
||tvdb_network||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series network||
||tvdb_banner_url||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series banner url||
||tvdb_fanart_url||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series fanart url||
||tvdb_poster_url||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series poster url||
||tvdb_airs_day_of_week||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series airs date of the week||
||tvdb_actors||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||List of series actors||
||tvdb_language||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series language(en, fr, etc.)||
||imdb_url||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Series imdb url||
||zap2it_id||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||||
||tvdb_ep_name||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Episode name||
||tvdb_ep_overview||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Episode plot||
||tvdb_ep_directors||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||List of episode directors||
||tvdb_ep_writers||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||List of episode writers||
||tvdb_ep_air_date||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Episode air date||
||tvdb_ep_rating||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Episode rating||
||tvdb_ep_guest_stars||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||List of episode guest stars||
||tvdb_ep_image_url||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Episode image url||
||tvdb_ep_id||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Episode season and number ie. [[S01E02]]||
||tvdb_season||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Episode season||
||tvdb_episode||[[thetvdb_lookup|Plugins/thetvdb_lookup]]||Episode number||
||trakt_series_name||[[trakt_lookup|Plugins/trakt_lookup]]||Series name provided by trakt||
||trakt_series_runtime||[[trakt_lookup|Plugins/trakt_lookup]]||Series runtime in minutes||
||trakt_series_first_aired_epoch||[[trakt_lookup|Plugins/trakt_lookup]]||Series premier data in epoch time||
||trakt_series_first_aired_iso||[[trakt_lookup|Plugins/trakt_lookup]]||Time stamp of premier date||
||trakt_series_air_time||[[trakt_lookup|Plugins/trakt_lookup]]||Time the series ran||
||trakt_series_content_rating||[[trakt_lookup|Plugins/trakt_lookup]]||Content rating ex: TV-14||
||trakt_series_genres||[[trakt_lookup|Plugins/trakt_lookup]]||Series genres||
||trakt_series_netowrk||[[trakt_lookup|Plugins/trakt_lookup]]||Series network||
||trakt_series_banner_url||[[trakt_lookup|Plugins/trakt_lookup]]||Series banner||
||trakt_series_fanart_url||[[trakt_lookup|Plugins/trakt_lookup]]||Series Fanart||
||trakt_series_poster_url||[[trakt_lookup|Plugins/trakt_lookup]]||Series poster||
||trakt_series_imdb_id||[[trakt_lookup|Plugins/trakt_lookup]]||Series IMDB ID||
||trakt_series_tvdb_id||[[trakt_lookup|Plugins/trakt_lookup]]||Series TVDB ID||
||trakt_series_tvrage_id||[[trakt_lookup|Plugins/trakt_lookup]]||Series TVRage ID||
||trakt_series_actors||[[trakt_lookup|Plugins/trakt_lookup]]||Series actors||
||trakt_series_country||[[trakt_lookup|Plugins/trakt_lookup]]||Production Country||
||trakt_series_year||[[trakt_lookup|Plugins/trakt_lookup]]||Series release year||
||trakt_series_status||[[trakt_lookup|Plugins/trakt_lookup]]||Series status(ex: Airing)||
||trakt_series_overview||[[trakt_lookup|Plugins/trakt_lookup]]||Series overview||
||trakt_ep_name||[[trakt_lookup|Plugins/trakt_lookup]]||Episode name||
||trakt_ep_first_aired_epoch||[[trakt_lookup|Plugins/trakt_lookup]]||Episode premier date in epoch||
||trakt_ep_first_aired_iso||[[trakt_lookup|Plugins/trakt_lookup]]||Episode premier date time stamp||
||trakt_ep_image_url||[[trakt_lookup|Plugins/trakt_lookup]]||Episode screenshot||
||trakt_ep_overview||[[trakt_lookup|Plugins/trakt_lookup]]||Episode overview||
||trakt_season||[[trakt_lookup|Plugins/trakt_lookup]]||Episode season||
||trakt_episode||[[trakt_lookup|Plugins/trakt_lookup]]||Episode Number||
||trakt_ep_id||[[trakt_lookup|Plugins/trakt_lookup]]||Episode id string '[[S01E01]]'||
||trakt_ep_tvdb_id||[[trakt_lookup|Plugins/trakt_lookup]]||TVDB ID of episode||
||trakt_watched||[[trakt_watched_lookup|Plugins/trakt_watched_lookup]]||Episode marked seen (true/false)||

^* = and other plugins that utilize this plugin^
