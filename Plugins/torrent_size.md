# Torrent size
**Removed in r1202, replaced by [[content_size|Plugins/content_size]]**

(XXX macro: "BR")
(XXX macro: "BR")
(XXX macro: "BR")

Reject torrents based on size. As this plugin only **Rejects**, you need to accept entries with some other filter (ie. [[accept_all], [wiki:Plugins/series series|Plugins/accept_all]] etc.)

### Example:


    torrent_size:
      min: 12
      max: 1200


Size is given in MB
