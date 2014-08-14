= IMDb list =

This plugin creates an [wiki:Entry Entry] for each item in an IMDb list.

This plugin is useful for example when used in a task with the [wiki:Plugins/queue_movies queue_movies] plugin to add movies from your IMDb watchlist to your [wiki:Plugins/movie_queue movie queue]

'''Notes:''' 

 * Like with other APIs used by !FlexGet the IMDb list is cached for 2 hours to avoid hammering.
 * List must be public.

'''Example:'''

{{{
imdb_list:
  user_id: ur9999999
  list: watchlist
}}}

Your user id can be found [http://www.imdb.com/list/watchlist here] when you are logged in.

'''{{{WARNING:}}}''' If you are using a list other than the 'watchlist', 'ratings' or 'checkins', you currently have to look up the list id from imdb and use that instead of the name. This problem is being tracked in ticket #1303

'''Note:''' Adding this to your movie tasks or preset will NOT cause movies in imdb's watchlist to be accepted since this is an input, not a filter.