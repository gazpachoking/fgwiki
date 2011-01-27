= RSS =

Parses any RSS feed.

== Simple configuration ==

{{{
rss: <url>
}}}

Note: https supported.

=== Basic http authentication ===

{{{
rss:
  url: <url>
  username: <name>
  password: <password>
}}}

=== Read from a file ===
You can also use local file instead of url.

''' Example '''

{{{
rss:
  url: /path/to/rss/something.xml
}}}

== Advanced usages ==

There are more advanced options that can be used with the rss plugin if you need them.

=== Link field ===
Incase RSS-feed uses some nonstandard field for {{{link}}} urls (ie. guid) you can
configure module to use url from any feedparser entry attribute.

'''Example'''

{{{
rss:
  url: <url>
  link: guid
}}}

You can also configure link with a list of fields. This will cause the download, deluge, and transmission plugins to fall back to later urls if there is a problem with the first. This can be especially useful if you are using the deluge or transmission plugin, and your feed provides a magneturi field. This example falls back on a magnet link if there is an error grabbing the direct torrent download. 

'''Example'''

{{{
rss:
  url: <url>
  link:
    - link
    - magneturi
}}}
'''Note:''' This example requires your feed provides the magneturi field, and that you are using an output plugin that can handle magnet uris.

=== Silent mode ===
You can disable few possibly annoying warnings by setting {{{silent}}} value to {{{yes}}} on feeds where there are
frequently invalid items.

'''Example'''

{{{
rss:
  url: <url>
  silent: yes
}}}

=== Group Links ===
If the feed has several links by item, you can set the {{{group_links}}} value to {{{yes}}}. This way, only one entry will be generated for the item, with all links attached to it.
Links are fields given by the {{{link}}} value plus enclosures, in that order.

The download plugin will then try to download each link until one works.

'''Example'''

{{{
rss:
  url: <url>
  group_links: yes
}}}

=== Capture other fields ===
If you want to keep information in another rss field attached to the flexget [wiki:Entry entry], you can use the {{{other_fields}}} option.

'''Example'''
{{{
rss:
  url: <url>
  other_fields: [date]
}}}

=== Convert to ASCII ===

Some feeds contain unicode characters which may cause problems. To force these into ASCII you set the {{{ascii}}} option to {{{yes}}}.

{{{
rss:
  url: <url>
  ascii: yes
}}}

=== Private trackers ===

Some trackers are private and require that you use some form of authentication. One might want to try using the [wiki:Plugins/headers headers] plugin.

{{{
header:
  cookie: 'uid=XXXXXXXXXXXXXXXX;pass=XXXXXXXXXXXXXXXXXXX'
rss:
  url: <url>
}}}