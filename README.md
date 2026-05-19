# Castle Defense

Castle Defense is a 3D real-time defense game made with Unity. During the day,
the player prepares defenses, hires soldiers, upgrades buildings, and clears
obstacles. At night, monsters attack the castle and the player must survive
until morning.

## Project

- Engine: Unity
- Platform target: Windows
- Genre: 3D, action, RTS, defense
- Build scenes:
  - `Assets/01_Scenes/Intro.unity`
  - `Assets/01_Scenes/Load.unity`
  - `Assets/01_Scenes/Main.unity`

## Gameplay

- Monsters normally move toward the castle.
- If the player enters an enemy's detection range, the enemy switches targets
  and chases the player.
- If an enemy reaches a fence or defensive structure, it stops and attacks it.
- The player can select soldiers and move them to a clicked tile.
- Soldiers stop moving and attack when enemies enter their range.

## Repository Notes

Generated Unity folders such as `Library`, `Temp`, `Logs`, and `UserSettings`
are ignored and should not be committed. Open the project from the repository
root in Unity, then use the scenes listed above for play testing or builds.
