## 1.0.7 (261116-01) - parked-artifact export for plugins

- New stdcall export `EMS_ParkedArt(hero, slot)`: while an artifact goes into or out of a new slot (equip, unequip, Altar of Sacrifice, Artifact Merchant) it passes through a normal slot of the same kind, and the artifact that normally sits there is set aside meanwhile. The export returns that set-aside artifact (or -1), so another plugin's equip-event handler knows the hero still has it. No change in play.

## 1.0.6 (261115-05) - portrait view flicker fix

- Fix (user report 261115): with Legend Heroes in the portrait view, the hero's artifacts flickered over the portrait while the mouse was outside the hero screen. Another handler showed the hidden artifact pictures again on every mouse move, and HASE hid them again and redrew the screen. Now the artifact pictures of the hero screen are simply not drawn in the portrait view, whatever shows them, and the extra redraw is gone.

## 1.0.5 (261115-04) - readme layout for the Mod Browser

- Readme laid out for the Heroes Launcher Mod Browser, which shows every line break of the file as a new line: each paragraph and bullet is one line now, long bullets are split into short sub-lists, and the ERM functions are a list instead of a code block. File names are in code quotes so they do not turn into web links. No change in play.

## 1.0.4 (261115-03) - Mod Browser release

- Hero screen: the name-panel place of the view switch is used only when it is free. With igrik's 10SSkills the hero's specialty icon sits there (item 118 at 250,30) - the switch then goes into the doll (left of the helmet) instead of covering the icon.
- Mod Browser / GitHub layout: readme renamed to `Readme.md` (mod.json `description.full`), `Screens\` with in-game screenshots, `.gitattributes`, mod.json `homepage` = the GitHub repository; short description without the old mod name.

## 1.0.3 (261115-02) - view switch in the name panel

- Hero screen: the view switch moved from the doll to the right end of the hero name panel (dialog 278,54), in both views. New settings [HeroScreen] SwitchInNamePanel (1 = name panel, the default; 0 = in the doll as in 1.0.2), PanelX / PanelY. The meeting screen keeps one switch in each doll.

## 1.0.2 (261115-01) - view switch inside the doll

- The view switch (Legend Heroes only) moved off Legend Heroes' button row, where it covered ERA Scripts' Night Scouting (Assassins) button, into the doll: the free cell left of the helmet, in both views.
- New 22x22 round gold switch with a gem-blue centre: its icon shows the view a click switches to (bust = portrait, grid = artifact slots), brighter while the mouse is over it, darker while pressed.
- Meeting screen: the switch sits in each hero's doll (was one button between the heroes); either one switches both.
- Settings: [HeroScreen] SwitchX / SwitchY (place inside the doll, default 83,14, used by both screens). The old keys [HeroScreen] ToggleX / ToggleY and [MeetingScreen] ToggleX / ToggleY are no longer read.
- Status bar: the hero and meeting screens now name the new slot (or the switch) under the mouse (the text was never shown before).
- Meeting screen: after switching from the portrait back to the slot view, native artifacts can be picked up and right-clicked again (before, only after reopening the screen).
- ToggleButton=0 keeps every screen (hero, meeting, merchant, altar) in the slot view; the remembered view is kept for when the switch is turned back on.
- The old switch picture `Data\Defs\emsview.def` is no longer used; when updating over an older version that folder can be deleted.

## 1.0.1 - readme layout

- Readme laid out for the Mod Manager's description panel (headings, lists, one bullet per change). No change in play.

## 1.0.0 - first full release

- First full release
