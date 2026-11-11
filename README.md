=====================================================================
 CLOSE MONUMENT ZOOM
 A camera mod for Sid Meier's Civilization VI
 Version 1.0  |  by Casul Game Studio LLC
=====================================================================

SUMMARY
---------------------------------------------------------------------
Lets you zoom the World View camera in MUCH closer to the action
(monuments, wonders, units, districts), and also zoom farther out than
the stock game. The camera tilts more toward the horizon when zoomed in
for a more immersive, "ground level" feel, and flattens out like a
map when zoomed far out.

This mod only replaces one file: Camera.artdef


WHAT IT CHANGES  (DEFAULT_CAMERA only)
---------------------------------------------------------------------
Values are shown as: Mod  (Stock)

Zoom height (World View altitude)
  Closest zoom ........ 14     (120)
  30% zoom point ...... 600    (n/a - added control point)
  Farthest zoom ....... 2500   (600)

Camera tilt (angle from straight down; higher = more toward horizon)
  Closest zoom ........ 65     (55)
  30% zoom point ...... 45     (n/a - added control point)
  Farthest zoom ....... 10     (45)

Strategic View zoom (number of hexes visible)
  Closest ............. 6      (3)
  Farthest ............ 32     (16)

Fog
  Fog is removed in the first part of the zoom range so close-ups
  stay crisp, and pushed back at far zoom so the map stays readable.

Field of view (FOV) is NOT changed: 45 degrees.

The "30% zoom point" squeezes the stock game's zoom behaviour into the
closest 30% of the scroll range, so the far-out range is all new.


INSTALLATION
---------------------------------------------------------------------
1. BACK UP the original file first. Copy:

     C:\Program Files (x86)\Steam\steamapps\common\
       Sid Meier's Civilization VI\Base\ArtDefs\Camera.artdef

   to somewhere safe. (Adjust the path if your Steam library is on
   another drive.)

2. Copy this mod's Camera.artdef into that same ArtDefs folder and
   allow it to overwrite the existing file.
   (If the downloaded file is named Camera_CloseMonumentZoom.artdef,
   rename it to exactly Camera.artdef first - the game only reads
   that name.)

3. Fully restart Civilization VI. Changes do not apply to a running
   game.

Mac / Linux: the folder layout differs from Windows (there may be no
"Base" folder; on some Linux installs the file lives under
steamassets/base/artdefs). This mod has only been prepared for the
Windows layout above and is untested on Mac/Linux.


UNINSTALL
---------------------------------------------------------------------
Copy your backed-up original Camera.artdef back over the modded one.
No backup? In Steam: right-click Civilization VI > Properties >
Installed Files > Verify integrity of game files. This restores the
stock file.


KNOWN ISSUES / NOTES
---------------------------------------------------------------------
- At the closest zoom, the camera sits very low. Depending on terrain,
  you may see ground/geometry clipping, especially near the edges of
  the map. If it bothers you, raise the closest-zoom height (see below).
- Zoom speed feels faster near the closest end because the whole
  low-altitude range is packed into the first 30% of the scroll wheel.
- Camera.artdef is replaced as a whole, so this mod is NOT compatible
  with other mods that replace Camera.artdef (for example KinetiKam,
  Farther Zoom, Free Camera). Use only one of them at a time.
- Game updates/patches may overwrite Camera.artdef. Re-apply the mod
  if your zoom returns to stock after an update.


TWEAKING IT YOURSELF
---------------------------------------------------------------------
Open Camera.artdef in a text editor that is not Notepad (e.g.
Notepad++). Everything is under Cameras > DEFAULT_CAMERA. Comments in
the file explain most values.

Closest zoom height (the one to change if you want closer/farther):
  Find the collection "HeightCurve", entry "HeightCurve1"
  (its Time is 0). Change its <m_fValue> for "Height".
    - Lower  = closer to the ground = closer zoom
    - Higher = farther back
    - 14 is the mod default; 20-40 is safer against clipping.
  Do not go much below ~10 - the camera NearClip is 10, so geometry
  starts getting cut off.

Closest zoom tilt:
  "TiltCurve" > "TiltCurve2" (Time 0), "Tilt". Values above ~65 can
  cause edge-of-map artifacts at low heights.

Strategic View zoom limits:
  "MinHexesVisible" and "MaxHexesVisible" near the top of
  DEFAULT_CAMERA.

Always keep a backup before editing.


CREDITS
---------------------------------------------------------------------
Close-up zoom tuning by Josh Reyes / Casul Game Studio LLC.

Sid Meier's Civilization VI is a trademark of Take-Two Interactive /
2K / Firaxis Games. This mod is unofficial and is not affiliated with
or endorsed by them.


CHANGELOG
---------------------------------------------------------------------
1.0  Initial release.
