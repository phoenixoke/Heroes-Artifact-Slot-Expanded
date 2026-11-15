# Heroes Artifact Slot Expanded 1.0.6

by Sinistral, co-authored by Claude

## DESCRIPTION

Heroes get 14 more artifact slots:

- misc: 7 new misc slots - 12 misc artifacts in all,
- rings: 4 new ring slots (below the two ring slots, and left / right of the boots),
- armour: a second armour slot (below the armour),
- weapon: a second weapon slot (beside the second necklace; the shield sits one row higher),
- necklace: a second necklace slot (below the necklace).

An artifact in a new slot works exactly like one in a normal slot of its kind: primary skills, special abilities, equip scripts, spells, combination parts. Every new slot can be switched off on its own.

## REQUIREMENTS

- HoMM3 ERA 3.9.x with WoG (ERA 3.9.29 or newer for the ERM functions below).

## COMPATIBILITY

- Any artifact the game counts as misc / ring / armour / weapon / necklace fits the matching new slot: vanilla, WoG, Emerald artifact mods (Third Upgrade Mod / ResOunD, JS - new artifacts), Advanced Classes Mod sets, Composite Artifact Expanded (composites can be forged / split in new slots).
- Works with HD mod (its trade buttons move the new slots too), Game Enhancement Mod artifact hints, ERA Spells, WoG option 730 (single-slot combination artifacts) and Hero Reserve Extended.
- Load it after Legend Heroes and ResOunD (mod.json `load_after`, which the ERA Mod Manager uses to sort the list).
- Two misc modes, chosen at game start (do not switch modes inside a running game):
  - catapult kept (vanilla, or Emerald with Enable6thSlot=0): 5 normal + 7 new misc slots;
  - Emerald's 6th misc slot on: 6 normal + 6 new.
- To keep the catapult with an Emerald mod, add "Enable6thSlot=0" to the Data\emerald.cfg of the Emerald mod highest in your mod list.

## HOW TO USE

- Install it from the Mod Browser, or unzip it into Heroes 3 ERA\Mods (folder name "Heroes Artifact Slot Expanded"), then enable it in the mod manager.
- Hero screen: misc slots 1-6 down the left column, 7-12 down the right one. The doll in the middle, rows top to bottom:
  - head;
  - cloak, necklace, shield;
  - weapon, second necklace, second weapon;
  - ring, armour, ring;
  - new ring, second armour, new ring;
  - new ring, boots, new ring;
  - war machines and spell book.
- Click a new slot with an artifact on the cursor to put it in, click it to pick the artifact up, right-click for the description. While you hold an artifact, every slot it fits lights up.
- Gained artifacts (map, battle loot, events, scripts) go into a free new slot of their kind when the normal ones are full (setting AutoEquip).
- Combination artifacts: parts in new slots count for assembling; a combination can be assembled into a new slot and taken apart from one (right-click; with WoG option 730 on: Ctrl+right-click).
- Meeting (trade) screen, artifact merchant, altar of sacrifice: the same layout, new slots included.
- View switch (Legend Heroes only): a small round gold button at the right end of the hero's name panel switches between the slot view and the full portrait.
  - Its icon shows the view a click switches to: a bust = the portrait, a grid = the slots.
  - In the portrait view no slots are shown; the merchant and altar then show Legend Heroes' own layout.
  - The meeting screen has the same button in each hero's doll, left of the helmet.
  - Put a held artifact down before switching.
  - If another mod already uses that place in the name panel (10SSkills puts the specialty icon there), the switch sits in the doll, left of the helmet.
- Without Legend Heroes the Commander and Hero Reserve buttons sit as small boxes left and right of the head slot.
- New slots everywhere:
  - luck / morale popups name the artifacts in new slots;
  - a defeated hero's new-slot artifacts go to the winner;
  - WoG Living Scrolls, Espionage, Adventure Cave and Artificer (misc slots) see the new slots;
  - Emerald per-artifact battle and daily effects work from new slots (Emerald 3.3 build: ResOunD / TUM 3.5.0).

## SETTINGS

Data\Heroes Artifact Slot Expanded.ini (every value is explained inside)

- [Slots] one switch per new slot (Misc1-Misc7, Ring1-Ring4, Armor, Weapon, Neck; 1 on, 0 off). A slot switched off has no slot and no frame on any screen; an artifact a game already has there goes to the hero's backpack when the game is loaded.
- [General] Enabled, AutoEquip, Debug (log detail), ScreenMessages (0 = no on-screen hints, the default).
- [HeroScreen] the view switch:
  - ToggleButton: 0 = no view switch, every screen keeps the slot view;
  - SwitchInNamePanel: 1 = name panel (default), 0 = in the doll;
  - PanelX / PanelY: place in the name panel, default 278,54 (move it if a very long class name runs under it);
  - SwitchX / SwitchY: place inside the doll, default 83,14 (meeting screen, and the hero screen when the switch is not in the name panel).
- Log: Runtime\Heroes Artifact Slot Expanded\hase_log.txt - please attach it to bug reports.

## ERM (read-only, ERA 3.9.29+)

Call: `!!SN:F^Heroes_Artifact_Slot_Expanded:`
`EMS_GetArt^/(hero)/(k);`
(any function below, with its parameters). The result is in v1.

- `EMS_SlotCount` - number of new slots (k = 0 to count - 1).
- `EMS_SlotKind/(k)` - 0 misc, 1 ring, 2 armour, 3 weapon, 4 necklace, -1 switched off.
- `EMS_GetArt/(hero)/(k)` - artifact in new slot k, or -1.
- `EMS_GetMod/(hero)/(k)` - its modifier (scroll spell), or -1.
- `EMS_FindArt/(hero)/(art)` - first new slot k holding that artifact, or -1.
- `EMS_CountArt/(hero)/(art)` - how many new slots hold that artifact.

`HE:A2`, `HE:A3` and `HE:F` (with /1) already include the new slots. Plugins can also use EMS_HeroScreenSlot, EMS_TakeArt and EMS_PutArt (stdcall exports).

## LIMITS

- WoG Artificer works on the new misc slots only.
- Before removing the mod from a running game, take the artifacts out of the new slots - otherwise they are lost and their bonus stays on the hero.

## CHANGES

Full list: `CHANGELOG.md`

**1.0.6**

- Fix: with Legend Heroes in the portrait view, the artifacts no longer flicker over the portrait while the mouse is outside the hero screen.

**1.0.5**

- Readme laid out for the Mod Browser (one line per paragraph and bullet, ERM functions as a list). No change in play.

**1.0.4**

- Hero screen: when another mod already uses the switch's place in the name panel (10SSkills' specialty icon), the switch sits in the doll instead.
- Screenshots, Mod Browser / GitHub layout (`Readme.md`, homepage).

**1.0.3**

- Hero screen: the view switch sits at the right end of the hero name panel (SwitchInNamePanel=0 puts it back in the doll).

**1.0.2**

- The view switch moved off Legend Heroes' button row into the doll, left of the helmet: ERA Scripts' Night Scouting (Assassins) button shows again.
- New round gold switch with a hover glow and a pressed look; its icon shows the view it switches to.
- Meeting screen: one switch in each hero's doll.
- Settings: new SwitchX / SwitchY; the old ToggleX / ToggleY keys are no longer read.
- Status bar names the new slot under the mouse (hero and meeting screen).
- Meeting screen: native artifacts can be picked up again right after switching back from the portrait.
- Updating: the folder `Data\Defs\emsview.def` is no longer used and can be deleted.

**1.0.1**

- Readme laid out for the Mod Manager's description panel (headings, lists, one bullet per change). No change in play.

**1.0.0**

- First full release.
