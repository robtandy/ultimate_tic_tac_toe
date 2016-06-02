# Ultimate Tic Tac Toe #

## Let's play! ##
This repo lets two programs play against each other in ultimate tic tac toe.
The managing program will decide which player goes first and turns go as
follows:
```
    while game not finished
        send game state to active player
        receive move
        check if game finished
        switch active player
```

## Rules ##
Ultimate Tic Tac Toe (UTTT) is played on a nested set of tic tack toe
gameboards.  Rules and gameplay can be found here
https://mathwithbaddrawings.com/2013/06/16/ultimate-tic-tac-toe .

Note that subboards that result in a tie result in neither X nor O 
occupying that spot on the board.

## Notation ##
We will refer to locations on a tic tac toe board numbered as such:
```
    1 | 2 | 3 
    ---------
    4 | 5 | 6
    ---------
    7 | 8 | 9
```

When we nest boards, we will refer to locations with the location the
largest board first.   So `11` is the upper left location in the upper
left subboard and `51` is the upper left location in the middle subboard.

## Player I/O ##
A player program needs to implement the following logic
```
    while game not finished
        read input
        break if end of game
        else respond with move
```
Possible input sent by the managing program is 
    * Game state as a string, if it is your program's turn, followed by a newline
    * a newline, if the game is over and your program should exit

### Game State ###
A string encoding of game state will look like the following
```
    11:  12:  13:O 14: 15:X 16: ....
```
That is, the coordinates of the subboard location, followed by an `X`, an `O`,
or a ` ` if it is unoccupied, followed by an additional space. 

Important: Your program is always `X` for ease of implementation.  The managing
program will keep track of who is X and O.  

### Making a move ###
To make a move print your move coordinates to stdout followed by a newline.

### Bad Input ###
If your program emits an illegal move (not a valid location, an occupied
location, or a location you are not allowed to currently choose), you will be
sent a newline in response (which you should treat as the end of the game).
The managing program should print out appropriate insults.


