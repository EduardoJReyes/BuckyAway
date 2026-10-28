# Bucky Away

Momentum-based 3D platformer for Steam (€1.99, 15-20 min). Bucky is a buttery, liquid orange
cat-blob and a courier who delivers mementos to the recently deceased. Three levels, three
deliveries, three ghosts. One rank per level, based on completion time. No other grading.

Team: Eduardo (tech director, design, levels, code), Luna (art director, animation, character),
Marc (rigging), Guillem (music, tech audio), Nerina (concept art).

## Project
- Unity 6, URP. Git + Git LFS (see .gitattributes). Main branch: `main`.
- Gameplay feel is the priority: movement, momentum, camera. Ask before changing tuning values.

## Folder layout (Assets/)
- `_Project/Scripts/` all game code, by feature: `Player/`, `Camera/`, `Levels/`, `UI/`, `Audio/`, `Core/`
- `_Project/Editor/` editor tools and import rules (AssetPostprocessor)
- `_Project/Art/` `Characters/`, `Environment/`, `Materials/`, `Shaders/`, `VFX/`
- `_Project/Prefabs/`, `_Project/Scenes/`, `_Project/Data/` (ScriptableObjects)
- Third-party packages stay out of `_Project/`.

## Naming
- Assets: `PREFIX_Name_v###` where needed. Prefixes: `CHR_` character, `RIG_` rig, `ANIM_` animation,
  `ENV_` environment, `PROP_` prop, `MAT_` material, `SH_` shader, `TEX_` texture, `UI_` UI, `SFX_` / `MUS_` audio,
  `LVL01_` level-specific.
- C#: PascalCase classes and public members, `_camelCase` private fields, one class per file,
  namespace `BuckyAway.<Feature>`.

## Rules
- Never edit `.unity`, `.prefab`, `.asset`, `.anim` or `.controller` files as text. Change them through the
  Unity editor (Unity MCP) or write an editor script that does it.
- Never touch `Library/`, `Temp/`, `Logs/`, `UserSettings/`.
- Always keep `.meta` files with their assets; never delete or regenerate them by hand.
- Prefer data in ScriptableObjects over hard-coded values, so designers can tune in the inspector.
- Prefer new Input System; gamepad must work everywhere.
- After code changes, check the Unity console for compile errors before saying a task is done.
- Small commits with clear messages. Don't commit or push unless asked.
