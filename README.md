# Unity Castle Defense

Unity Castle Defense is a 3D real-time castle defense game made with Unity. The
player prepares defenses during the day, then protects the castle from monster
attacks at night.

## Gameplay

- Build and upgrade defenses.
- Hire and command soldiers.
- Clear obstacles from the battlefield.
- Defend the castle through the night.
- Survive until morning to continue.

## Controls

- Left mouse drag: rotate the camera.
- Mouse wheel: zoom in and out.
- Right click: select buildings, soldiers, and obstacles.
- Select a soldier, then click a destination to move it during battle.

## Requirements

- Unity Editor version listed in `ProjectSettings/ProjectVersion.txt`
- Windows build support for Unity
- Git

## Project Structure

```text
Assets/
  01_Scenes/       Game scenes
  02_Scripts/      Gameplay and UI scripts
  03_Prefabs/      Game prefabs
  04_Materials/    Materials
  05_Texture/      Textures and UI images
  06_Sounds/       Music and sound effects
  07_Mesh/         Mesh assets
  08_MyAssets/     Imported art and asset packs
  09_Animations/   Animations and controllers
  10_Fonts/        UI fonts
Packages/          Unity package files
ProjectSettings/   Unity project settings
```

## Scenes

The project uses these main scenes:

```text
Assets/01_Scenes/Intro.unity
Assets/01_Scenes/Load.unity
Assets/01_Scenes/Main.unity
```

## How To Open

1. Open Unity Hub.
2. Add this project folder.
3. Open the project with the Unity version listed in
   `ProjectSettings/ProjectVersion.txt`.
4. Open `Assets/01_Scenes/Intro.unity`.
5. Press Play.

## Build

1. Open `File > Build Settings`.
2. Make sure the scenes listed above are included in the build.
3. Select the target platform.
4. Click `Build`.

## Repository

Generated Unity folders should not be committed:

```text
Library/
Temp/
Obj/
Build/
Builds/
Logs/
UserSettings/
```

These folders are ignored by `.gitignore`.

## License

Check the licenses of included third-party assets before publishing or
distributing a build.
