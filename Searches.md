# Search Plugins

FlexGet provides framework for plugins meant for querying searches from supported sites. These can be used with the [[urlrewrite_search] & [wiki:Plugins/discover discover|Plugins/urlrewrite_search]] plugins where they act like options for their parent plugins. This page lists these options and gives a brief description of their function.


## Overview 

||**Keyword*'||'*Description**||
||[[btn|Searches/btn]]||Searches private torrent site BTN||
||[[cpasbien]||Generates entries from [http://www.cpasbien.pw/ cpasbien.pw|Searches/cpasbien]]||
||[[flexget_archive|Searches/flexget_archive]]||Searches within previously archived entries||
||[[freshon]||Generates entries from [http://freshon.tv freshon.tv|Searches/freshon]]||
||[[iptorrents]||Generates entries from [http://iptorrents.com iptorrents.com|Searches/iptorrents]]||
||[[isohunt]||Generates entries from [http://isohunt.com isohunt.com|Searches/isohunt]]||
||[[kat]||Generate entries from [http://kat.ph kat.ph|Searches/kat]]||
||newtorrents||Generates entries from [[newtorrents.info|http://newtorrents.info]]||
||newzleech||Broken as Newzleech.com is no more||
||[[newznab]||Generates entries from [http://newznab.com newznab.com|Searches/urlrewrite_newznab]]||
||[[nyaa]||Generates entries from [http://nyaa.se/ nyaa.se|Searches/nyaa]]||
||[[piratebay]||Generates entries from [http://thepiratebay.gl/ thepiratebay|Searches/piratebay]]||
||[[ptn|Searches/ptn]]||Searches private torrent site PtN||
||[[publichd]||Generates entries from [http://publichd.se/ PublicHD|Searches/publichd]]||
||[[rarbg]||Generates entries from [http://rarbg.com/ RarBG|Searches/rarbg]]||
||[[sceneaccess|Searches/sceneaccess]]||Searches private torrent site sceneaccess||
||[[search_rss|Searches/search_rss]]||Generates query based rss feeds||
||[[torrent411]||Generates entries from [http://www.t411.me/ t411.me|Searches/t411]]||
||torrentshack||Searches private torrent site torrentshack||
||[[torrentleech]||Generates entries from [http://torrentleech.org/ torrentleech.org|Searches/torrentleech]]||
||[[torrentz]||Generates entries from [http://torrentz.eu torrentz.eu|Searches/torrentz]]||
||whatcd||Searches private torrent site whatcd||


You can always get an up to date overview of the available search plugins by using the command line. On Flexget>=1.2, the command is now 'flexget plugins --group search', and documentation for a plugin can be obtained with 'flexget doc <plugin-name>'.
** Example **

    flexget plugins --group search
    -- Supported search plugins: --------------------------------------------------
     search_rss
     piratebay
     newzleech
     flexget_archive
     newtorrents
     torrentz
    -------------------------------------------------------------------------------

