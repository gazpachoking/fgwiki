= Upgrading 1.0 installation =

If you're still using 0.9 see [wiki:MigrateTo10 this].

== Check current version ==

Start by checking what version you currently have with command:

{{{
flexget -V
}}}

Subversion users must use `svnversion .` in checkout directory instead.

Write this somewhere down.

== Upgrade ==

If you have short cron interval, comment !FlexGet out from the cron. After you've ran successfully manually, put it back.

Install new version like you installed it first place

{{{
easy_install <new egg>
}}}

Subversion users can just run `svn up`.

== Changes ==

See [wiki:BleedingEdge bleeding edge news] and see if there are any steps that you must do, if you have several months old version there are almost certainly some changes that need you to take some actions.

For example, if you were running r904 follow all the steps from this revision upwards. Usually this means running some sqlite3 commands or modifying configuration file.