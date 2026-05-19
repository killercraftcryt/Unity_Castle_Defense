# Unity Castle Defense

Unity Castle Defense is a 3D real-time defense game built with Unity. The player
prepares during the day by buying buildings, hiring soldiers, upgrading defenses,
and clearing obstacles. At night, monsters attack the castle and the player must
survive until morning.

## Current Status

This project was cleaned up for a new English-language repository:

- In-game Korean UI instructions were translated to English.
- Korean UI fonts were replaced with existing English fonts.
- Main menu labels were updated from lowercase text to clearer English labels.
- Old project README links, video links, download links, and previous repository
  references were removed.
- Unused demo scenes, sample folders, welcome screens, old README images, and
  unused Korean font assets were removed.
- Build scenes still remain in the project.

The project still needs a full Unity Editor test pass before publishing a release
build.

## Requirements

- Unity Editor version matching `ProjectSettings/ProjectVersion.txt`
- Windows target platform support
- Git
- Git LFS is recommended if the repository grows with large binary assets

## Project Structure

```text
Assets/
  01_Scenes/       Main playable scenes
  02_Scripts/      Gameplay, UI, enemy, player, audio, and upgrade scripts
  03_Prefabs/      Buildings, enemies, effects, UI objects, and gameplay prefabs
  04_Materials/    Materials used by models and effects
  05_Texture/      UI and gameplay textures
  06_Sounds/       Background music and sound effects
  07_Mesh/         Mesh assets
  08_MyAssets/     Third-party art and asset packs used by the game
  09_Animations/   Animation clips and animator controllers
  10_Fonts/        English fonts used by UI text
Packages/          Unity package manifest and package lock
ProjectSettings/   Unity project configuration
```

## Build Scenes

The active build scenes are:

```text
Assets/01_Scenes/Intro.unity
Assets/01_Scenes/Load.unity
Assets/01_Scenes/Main.unity
```

Check `ProjectSettings/EditorBuildSettings.asset` if a scene is missing from the
Unity Build Settings window.

## Gameplay Summary

- The castle is the main objective.
- Monsters move toward the castle by default.
- If the player enters an enemy detection range, the enemy can switch target and
  chase the player.
- If an enemy reaches a barricade, wall, or defensive object, it stops and attacks.
- The player can select soldiers and send them to clicked tiles.
- Soldiers stop moving and attack when enemies enter their range.
- Buildings and soldiers can be upgraded.
- Obstacles block building placement and unit movement until removed.

## Basic Controls

These controls are shown in the in-game help UI:

- Left mouse drag: rotate the camera.
- Mouse wheel: zoom in and out.
- Right click: select buildings, soldiers, and obstacles.
- Select a soldier, then click a destination to move it during battle.

## How To Open The Project

1. Open Unity Hub.
2. Click `Add` or `Open`.
3. Select this project root folder.
4. Let Unity import assets and rebuild the `Library` folder.
5. Open `Assets/01_Scenes/Intro.unity`.
6. Press Play and test the flow from intro to loading to the main game.

## What To Test Before Publishing

Run through this checklist in Unity:

- Intro scene starts correctly.
- Start button loads the loading scene.
- Loading scene loads the main scene.
- Main scene UI text is readable and fully in English.
- Camera rotation and zoom work.
- Player movement works.
- Enemy spawning works.
- Enemies target the castle, player, and defenses correctly.
- Building placement works.
- Soldier hiring and movement work.
- Upgrade windows open and apply upgrades correctly.
- Selling buildings works.
- Obstacle removal works.
- Sound and music buttons work.
- Game over and victory flows work.
- No missing scripts, missing prefabs, or missing materials appear in the console.

## Known Cleanup Notes

The project was reduced by deleting demo-only content from imported asset packs.
Runtime assets used by the active game scenes were kept. After opening the project
in Unity, check the Console window for missing references. If Unity reports a
missing asset, restore only the specific file needed by the active scene or prefab.

The old remote repository URL was removed because it pointed to the previous
project source. Add your own repository URL before pushing.

## What Should Be Fixed Next

Recommended code and project cleanup:

- Fix spelling in object names and code identifiers:
  - `Baricade` should become `Barricade`.
  - `Balista` should become `Ballista`.
  - `ShiledBearer` should become `ShieldBearer`.
  - `Diamage` should become `Damage`.
  - `RughtButton` should become `RightButton`.
- Replace string comparisons for building types with enums or ScriptableObjects.
- Move repeated UI text and prices into data assets.
- Add a small localization system if more languages will be supported later.
- Split large manager classes if they contain unrelated responsibilities.
- Add null checks and clearer error logs around UI references and spawned prefabs.
- Review third-party asset licenses before a public release.
- Remove unused audio files after confirming which clips are referenced by scenes.
- Run Unity's `Assets > Reimport All` once after cleanup.
- Create a Windows build and test it outside the Unity Editor.

Recommended gameplay improvements:

- Add a pause menu.
- Add a settings menu with music and sound volume sliders.
- Add a tutorial or first-day guidance.
- Add clear win and lose screens with restart and main menu buttons.
- Add balancing data for enemy waves, rewards, and upgrade prices.
- Add visual feedback for invalid building placement.
- Add health bars or clearer damage feedback for important units and buildings.

## Git Repository Notes

Do not commit generated Unity folders:

```text
Library/
Temp/
Obj/
Build/
Builds/
Logs/
UserSettings/
```

These folders are already ignored by `.gitignore`.

### Should `.git` Be Deleted?

Usually, no.

Keep `.git` if you want to preserve the current commit history and continue from
the cleanup commit. This is the recommended option.

Delete `.git` only if you want to completely remove the old history and create a
brand-new repository with a single first commit. If you delete `.git`, Git will
forget all previous commits, branches, and remote settings.

### Should `.gitattributes` Be Deleted?

No. Keep `.gitattributes`.

It currently normalizes text file line endings:

```text
* text=auto
```

That is useful for a Unity project shared between Windows and other systems. You
can improve it later with Unity-specific rules for binary assets, but do not
delete it without a reason.

## Creating The `Unity_Castle_Defense` Repository

Recommended path: keep the current `.git` history and add a new remote.

```powershell
git status
git remote -v
git remote add origin https://github.com/YOUR_USERNAME/Unity_Castle_Defense.git
git push -u origin codex/cleanup-localization
```

Then, on GitHub, you can either:

- keep `codex/cleanup-localization` as the main branch, or
- open a pull request into `main`, or
- rename the local branch to `main` before pushing:

```powershell
git branch -M main
git push -u origin main
```

Alternative path: create a completely fresh repository without old history.

```powershell
Remove-Item -Recurse -Force .git
git init
git add .
git commit -m "Initial Unity Castle Defense project"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/Unity_Castle_Defense.git
git push -u origin main
```

Use the fresh-history option only if you are sure you do not need the old commit
history.

## Current Branch

The cleanup work was prepared on:

```text
codex/cleanup-localization
```

Cleanup commit:

```text
bf83bc8 Clean up localization and unused demo assets
```

Before pushing, check `git status` and decide whether any remaining local changes
should be committed, ignored, or reverted.
