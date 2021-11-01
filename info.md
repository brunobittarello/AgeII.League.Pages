## Explain how it works

This script uses aoe2.net API to import data from the top 200 players last 1000 ranked matches, storing only games between players.
</br>
The first season placement is based on the rankings recorded in 2020-10-16. Next season works with promotes/demotes.
</br>
The algorithm compares all games between players in the division where the date is inside the season period. A win means a goal for the player. If a player gets more goals in a game, it is a victory in league.
</br>
3 points for victory, and 1 point for draw. The Tiebreaker criteria is the number of wins, than goals foward.

## Alias, Smurfs and Dead accounts

Many player has more than one account. Capoch has 4 as far as what I was able to find! I managed to merge matches from any additional account to the main account, cleaning up some duplicated players along the divisions. I'm not a age of empires 2 expert to know every player's alternative accounts, so if there is a alternative account in any division, please let me know.

</br>

Some players stop playing for some time, or even give up playing with an account. This reflects in a 0w-19d-0l season performance, that leads for a 19 points for doing nothing. I'm thinking about to give 0 points for draws from a 0-0 match up. Or give 0 points for players with 19 draws. Maybe it will be applied in the next bake.

## Future implementations

* Add 4 new players from no division in the last division
* Add some new statistics (biggest score, favorite civ, position through seasons...)
* If I can get access to older data from aoe2.net, I can compute the first season even before 2020-06-01

## Technical information

All those tables were created using PHP 7.4.1 with Laravel 8.62 and MySql. Source code is in a private repository.

## Acknowledgment

* https://aoe2.net - All was posible because of this service. That API was very useful and easy to use. Big thanks.
* https://liquipedia.net - Because many players uses many accounts, I had to find each one of them and merge into one data. This site helped me showing the "Alternate ID" for some players.
* [Identifying Smurfs in the 1v1 RM Ladder](https://www.aoezone.net/threads/identifying-smurfs-in-the-1v1-rm-ladder.168896/) - This topic helped me with the smurfs accounts as well. Thanks!
* [Using details in GitHub](https://gist.github.com/ericclemmons/b146fe5da72ca1f706b2ef72a20ac39d) - To show how to use < details > nested. Markdown in github is tough...
