# Trakt Add
**`IMPORTANT:` Please see [[trakt|Plugins/trakt]] on how to authorize Flexget to access your private Trakt.tv account.**

This plugin will add accepted movies/tv episodes to one of your [[trakt.tv|http://trakt.tv]] lists.

This plugin can be added to any of your tasks that deal with movies/series, or it can be used with the [[filesystem|Plugins/filesystem]] plugin to add all your already acquired episodes/movies on trakt.tv to a specified list.

Please note that `account` is **required**.
**Configuration:**


    trakt_add:
      username: <trakt username>
      account: <flexget account name>
      list: <list name>


The `list` option can be one of the built in trakt lists, `collection`, `watched`, or `watchlist`, or the name of one of your custom trakt lists.
