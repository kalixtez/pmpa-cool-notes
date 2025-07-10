Flag 9 was a bit confusing at first. Seems like you can access to it using the `https://injuredandroid.firebaseio.com/flags.json` and also the `https://injuredandroid.firebaseio.com/flags/.json`. Looks like that can also be done with the `sqlite` path of the database. Might have something to do with how Firebase stores objects in the realtime database. Both `/something` and `/something/.json` seem to retrieve the exact same thing.

Reaching to one of those endpoints will yield a single answer: `[nine!_flag]`. This is not the correct answer, as the program expects the B64 encoding of this value:

Ninth flag:

`W25pbmUhX2ZsYWdd`