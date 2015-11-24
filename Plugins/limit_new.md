# Limit New

Limit number of new items.

Example:


    limit_new: 1


This would allow only one new item to pass trough per execution.
Useful for passing torrents slowly into download, especially when adding new sources which would result massive concurrent downloads.
(XXX macro: "BR")(XXX macro: "BR")
Note that since this is per execution, actual "flow rate" depends how often
FlexGet is executed.
(XXX macro: "BR")(XXX macro: "BR")
Equivalent of poor mans queue for clients which do not support such feature.
