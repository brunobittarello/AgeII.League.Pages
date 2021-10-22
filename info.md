## Explain how it works

I get the top 200 player in ranked and its 1000 last games from aoe2.net API. My script import this data and store only games between players stored.
</br>
The first season placement is based on the rank position in 2020-10-16. Next season goes with promotes/demotes.
</br>
The algorithm compares all games between player in the division were the date is inside the season period. A win means a goal for the player. If a player gets more goals in a game, it is a victory in league.
</br>
3 points for victory, and 1 point for draw. The Tiebreaker criteria is wins, than goals foward.

## Alias, Smurfs and Dead accounts

Many player has more than one account. Capoch has 4 as far as I mapped! I managed to merge matches from any aditional account to the main account, cleaning up some duplicated players along the divisions. I'm not a age of empires 2 expert to know every alternative accounts, so if there is a alternative account in any division, please let me know.

</br>

Some players stop to player for some time. Or give up from playing in a account. The result is a player that performs 0w-19d-0l in a season, that leads for a 19 points for doing nothing. I'm thinking about to give 0 points for draws from a 0-0 match up. Or give 0 points for players with 19 draws. Maybe it will be applied in the next bake.

## Future implementations

* Add 4 new players from no division in the last division
* Add some new statics (biggest score, favorite civ, position through seasons...)
* If get access for a older data from aoe2.net, I can compute the first season even before 2020-06-01

## Technical information

All those tables were created using PHP with Laravel 8.62 and MySql. Source code is in a private repository.

## Acknowledgment

* https://aoe2.net - All was posible because of this service. That API was very useful and easy to use. Big thanks.
* https://liquipedia.net - Because many players uses many accounts, I had to find each one of them and merge into one data. This site helped me showing the "Alternate ID" for some players.
* [Identifying Smurfs in the 1v1 RM Ladder](https://www.aoezone.net/threads/identifying-smurfs-in-the-1v1-rm-ladder.168896/) - This topic helped me with the smurfs accounts as well. Thanks!
* [Using details in GitHub](https://gist.github.com/ericclemmons/b146fe5da72ca1f706b2ef72a20ac39d) - To show how to use < details > nested. Markdown in github is tough...
