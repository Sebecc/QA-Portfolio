#  Player character falls below the map after teleporting during gliding

## Summary

The issue occurs when playing as Lynae. Teleporting during gliding causes the player character to fall below the map instead of remaining on the terrain.

## Environment

- Platform: PC
- Operating System: Windows 11
- Game Version: 3.2
- Reproducibility: 2/2 

## Preconditions

- Player is logged in
- Lynae is selected
- Teleport waypoint is unlocked

## Steps to reproduce

1. Launch the game.
2. Select Lynae as the active character.
3. Start gliding.
4. Teleport to the waypoint shown in the attached video.
5. Wait for the loading screen to finish.
6. Observe the character's position.

## Expected result

The player character should remain on the terrain after teleporting.

## Actual result

The player character is located below the terrain after teleporting and is able to glide underneath the map.

## Severity

Medium

# Priority

Medium

## Evidence

See videos
- Video 1 – Control test using another character (issue not reproduced)


![Evidence Video 1](Video%20Evidence/01_Other_Character_No_Issue.gif)
  
- Video 2 – Bug reproduction using Lynae


![Evidence Video 1](Video%20Evidence/02_Lynae_Bug.gif)

- Video 3 – Second successful reproduction using Lynae

  
![Evidence Video 1](Video%20Evidence/03_Lynae_Bug_Second_Attempt.gif)
