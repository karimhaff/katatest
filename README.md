The best way to run my code is in a Jupyter Notebook environment.





# The Goose Game Kata
Goose game is a game where two or more players move pieces around a track by rolling a die. The aim of the game is to reach square number sixty-three before any of the other players and avoid obstacles. ([wikipedia](https://en.wikipedia.org/wiki/Game_of_the_Goose))

This kata has been invented by [Matteo Vaccari](https://github.com/xpmatteo), you can find the original slides [here](https://www.slideshare.net/pierodibello/il-dilettevole-giuoco-delloca-coding-dojo).

As well, this repository is a fork of [Xpeppers](https://github.com/xpeppers/goose-game-kata/).

## General requirements
- You should use Python, at least version 3.7.
- You should commit your code on GitHub or any other SCM repository you prefer (e.g. bitbucket, gitlab, etc) and send us the link. In this way, we will be able to review it but also discuss it.
- You should release your work under an OSI-approved open-source license of your choice.
- You should deliver the sources of your application, with a README that explains how to run it.
- You can modify the text of the printed messaged. However, the meaning must still be the same.

**IMPORTANT:**
- Implement the requirements focusing on writing the best code you can produce.
- Take 15 minutes to understand the task.
- Do not take more than 2 hours to develop the code of this Kata.

## Features

### 1. Add players
As a player, I want to add me to the game so that I can play.

**Scenarios:**
1. Add Player
   ```shell
   If there is no participant
   the system asks: "Add player:"
   the user writes: "Pippo"
   the system responds: "players: Pippo"
   the system asks: "Add player:"
   the user writes: "Pluto"
   the system responds: "players: Pippo, Pluto"
   ```

2. Duplicated Player
   ```shell
   If there is already a participant "Pippo"
   the system asks: "Add player:"
   the user writes: "Pippo"
   the system responds: "Pippo: already existing player"
   ```

4. We add as many players we want to
   
3. Once, no more players are added. The game will start.

### 2. Move a player


**Scenarios:**
1. Start
   ```shell
   If there are two participants "Pippo" and "Pluto" on space "Start"
   the system asks: "Pippo rolls:"
   the user writes: "4,2"
   the system responds: "Pippo rolls 4,2. Pippo moves from Start to 6"
   the system asks: "Pluto rolls:"
   the user writes: "2,2"
   the system responds: "Pluto rolls 2,2. Pluto moves from Start to 4"
   the system asks: "Pippo rolls:"
   the user writes: "2,3"
   the system responds: "Pippo rolls 2,3. Pippo moves from 6 to 11"
   ```

### 3. Win
As a player, I win the game if I land on space "63"

**Scenarios:**
1. Victory
   ```shell
   If there is one participant "Pippo" on space "60"
   the system asks: "Pippo rolls:"
   the user writes: "1,2"
   the system responds: "Pippo rolls 1,2. Pippo moves from 60 to 63. Pippo Wins!!"
   ```

2. Winning with the exact dice shooting
   ```shell
   If there is one participant "Pippo" on space "60"
   the system asks: "Pippo rolls:"
   the user writes: "3,2"
   the system responds: "Pippo rolls 3,2. Pippo moves from 60 to 63. Pippo bounces! Pippo returns to 61"
   ```
### 4. The game throws the dice
As a player, I want the game throws the dice for me to save effort

**Scenarios:**
1. Dice roll.
   ```shell
   If there is one participant "Pippo" on space "4", 
   assuming that the dice get 1 and 2
   the system asks: "Pippo rolls:"
   when the user writes: ""
   the system responds: "Pippo rolls 1,2. Pippo moves from 4 to 7"
   ```

### 5. Space "6" is "The Bridge"
As a player, when I get to the space "The Bridge", I jump to the space "12"

**Scenarios:**
1. Get to "The Bridge"
   ```shell
   If there is one participant "Pippo" on space "4"
   assuming that the dice get 1 and 1
   the system asks: "Pippo rolls:"
   when the user writes: ""
   the system responds: "Pippo rolls 1,1. Pippo moves from 4 to The Bridge. Pippo jumps to 12"
   ```

### 6. If you land on "The Goose", move again
As a player, when I get to a space with a picture of "The Goose", I move forward again by the sum of the two dice rolled before

The spaces 5, 9, 14, 18, 23, 27 have a picture of "The Goose"

**Scenarios:**
1. Single Jump
   ```shell
   If there is one participant "Pippo" on space "3"
   assuming that the dice get 1 and 1
   the system asks: "Pippo rolls:"
   when the user writes: ""
   the system responds: "Pippo rolls 1,1. Pippo moves from 3 to 5, The Goose. Pippo moves again and goes to 7"
   ```

2. Multiple Jump
   ```shell
   If there is one participant "Pippo" on space "10"
   assuming that the dice get 2 and 2
   the system asks: "Pippo rolls:"
   when the user writes: ""
   the system responds: "Pippo rolls 2,2. Pippo moves from 10 to 14, The Goose. Pippo moves again and goes to 18, The Goose. Pippo moves again and goes to 22"
   ```

### 7. Prank (Optional Step)
As a player, when I land on a space occupied by another player, I send him to my previous position so that the game can be more entertaining.

**Scenarios:**
1. Prank
   ```shell
   If there are two participants "Pippo" and "Pluto" respectively on spaces "15" and "17"
   assuming that the dice get 1 and 1
   the system asks: "Pippo rolls:"
   when the user writes: ""
   the system responds: "Pippo rolls 1,1. Pippo moves from 15 to 17. On 17 there is Pluto, who returns to 15"
   ```
