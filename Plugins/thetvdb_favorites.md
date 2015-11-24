# Thetvdb Favorites

This plugin is mainly used from the [[configure_series] plugin to automatically configure FlexGet to download all of your tvdb favorites. The plugin works as input that returns entries for all the shows you have marked as favorites at [http://thetvdb.com|Plugins/configure_series]]. If thetvdb goes down, the last known list of favorites will be used until it comes back online. 

You configure thetvdb_favorites plugin with your account id at thetvdb. You can find it on the [[account tab|http://thetvdb.com/?tab=userinfo]] after you log in.
** Example **


    configure_series:
      from:
        thetvdb_favorites:
          account_id: 320[[D93B3A1]]


## Strip Dates Option

If the `strip_dates` option is specified, the trailing year will be stripped from series names that include them. For example, "Merlin (2008)" would become just "Merlin".
** Example **

    thetvdb_favorites:
      account_id: 320[[D93B3A1]]
      strip_dates: yes


## Series Settings

You can use any of the [[settings] of the series plugin with the [wiki:Plugins/configure_series configure_series|Plugins/series#Settings]] plugin, as shown below.
** Example **


    configure_series:
      from:
        thetvdb_favorites:
          account_id: 320[[D93B3A1]]
      settings:
        timeframe: 12 hours
        target: 720p
        propers: 3 days

