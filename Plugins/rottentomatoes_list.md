# Rotten Tomatoes List

Emits an entry for each movie in a [[Rotten Tomatoes|http://www.rottentomatoes.com]] list.

### Configuration

        rottentomatoes_list:
            api_key: rh8chjzp8vu6gnpwj88736uv
            dvds:
              - top_rentals
              - upcoming
            movies:
              - box_office


You should [[http://developer.rottentomatoes.com/|create]] and use your own API key instead of the default, as Rotten Tomatoes limits the number of concurrent users per key.
** Possible lists are **
* dvds:
* top_rentals
* current_releases
* new_releases
* upcoming
* movies
* box_office
* in_theaters
* opening
* upcoming
