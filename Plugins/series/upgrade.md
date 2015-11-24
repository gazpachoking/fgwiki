# Upgrade

Upgrade mode causes the series plugin to continue getting the best quality of an episode it sees. It also blocks any episodes that are of a worse quality than you already have. It can be used alongside the [[qualities] option or [wiki:Plugins/series/quality quality|Plugins/series/qualities]] options to restrict which qualities will be upgraded to.

## Example


    series:
      - name of the series:
          upgrade: yes
          qualities:
            - hdtv
            - hdtv 720p

