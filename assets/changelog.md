# Changelog  

todo: particles, dash, tall grass destruction, tall grass rotation, texture atlas everything
 make slimes drop items, make arrows finite, flash step, animate slimes, daynight cycle
#### Date: 12/9/2025
- made and added kunai-ui.png
- made and added kunai.png
- made and added grass.png

#### Date: 11/9/2025
- removing completely old tall grass logic to make way for rework
- i: after playtesting memory seems to stop leaking after a while, so thats a good sign, still needs improvement tho

#### Date: 7/9/2025
- improved debug display with enemy, particles and projectiles count with memory usage
- improved fps: used dirty flags to recreate enemies array instead of every second
- ! memory usage only keeps increasing - memory leak detected - my computer fans is genuinely scaring me im closing tab to force memory cleanup and let my computer breathe, must fix this asap, also this causes fps drop and lag :/
- removed duplicate function that was there somehow

#### Date: 5/9/2025
- added day/night cycle but made it dormant because it needs finetuning and polish, will be reactivated when other more important features are added first, decent attempt tho

#### Date: 4/9/2025
- fixed: chunk enemy ownership not transferred properly, leading to enemies randomly dying when their birth chunk is offloaded, fixed by using the official world generation function to move the enemy, silly me
- added shadow kunai teleportation but it feels unsatisfying right now, will fix
  - added trail particles
  - made them last longer and be bigger, so much better
  
#### Date: 29/8/2025
- ! flash white not working - 2fix: nade it work by removing settimout dependency
- ! arrows dont make piercing type particles - fix: passed shoot attacktype to takedamage()
- made slimes face player during movement using same sprite
- ! **fps so slow**:
  - fix 1: update enemies if theyre close enough to the player
    - crude but will replace with line of sight checks later
    - fixes all enemies being updated every frame from literally across the existing world
  - fix 2: added *bucketing* to the texture cache so the random size generation doesnt make infinite combinations
    - also added *cache cleaning* so it doesnt accumulate over time - a big issue previously causing fps to drop slowly


#### Date: 28/8/2025
- *summary: art / assets updates*
- made a sword.png and a bow.png and imported it into the inventory ui.
- ! *looks distorted* - **fix: PIXI.SCALE_MODES.NEAREST**, now looks too small, **fix: scale it using code**
- made an arrow.png for arrow projectiles, imported it into projectile.js
- made bow and arrow mechanics more realistic (created when pressed, pulled back and released visually) for both MSB clicks
- made bow rotate towards mouse & made weaponRenderer.js
- **removed tall grass temporarily to try reduce lag but still very high lag, will fix soon, have a list of problems**
- ! improved arrow hitbox logic and fixed quantum *tunneling* because arrow moves through enemies between frames and collisions are undetected, fix: use raycasting *sensibly*


---
### UPDATE 22/8/2025 V4

#### Date: 20/8/2025
- made particles work, added precise bool to attack types, 
- precise attacks send particles through enemies, non precise send them perpendicular
- enemy explodes in particles upon death 
- ! **fps so slow** <<<<<<<<<<====================================
- ! *particles look mid not bad but not good*
- added working chunk border debug mode

#### Date: 19/8/2025
- made projectile.js and a bow and arrow system
- ! arrows do not point in the direction they are fired and do not delete themselves after first hit
- fixed arrows pointing in direction theyre fired and delete themselves after first hit
- ! arrows did not do knockback - fixed: too much knockback - fixed: reduced knockback to 0.2
- ! charge system for bow and arrow didnt work: used max power - fixed charge system, works now
- ! somehow cooldown had been reset and my code was reverted and I cant undo, must reimplement cooldown
- **fixed global cooldowns**
- **added hotkeys** to quickly rotate and equip inventory items, inventoryUI.js now listens for inventory.js's events

#### Date: 18/8/2025  
- Added tall grass with sine-wave sway animation (anchored at bottom)  
- Added player interaction with grass  
- Implemented painters algorithm so player renders behind grass  
- Reduced grass blades from 3 to 2 (looked cleaner)  
- Made tallGrass.js and refactored combat logic from player.js into combat.js
- made inventory.js and inventoryUI.js, made equipping and unequpping weapons work
- added the inventory placeholder bar

#### Date: 16/8/2025  
- Improved sword slash visuals ↔ hitbox consistency  
- Added damage frames to slimes when hit  
- Added knockback to slimes on hit  
- ! Another failed dash attack attempt (scrapped)  

---
### UPDATE 22/8/2025 V3

#### Date: 15/8/2025  
- **Removed edges entirely** — wasn’t worth fixing the neighbor bug  
- Improved grass tile sprites + added 3 variations  
- grass variations in a texture atlas
- Grass variations now random but **fixed per tile** (no more flickering)  
- Added slime enemies:  
  - Hitboxes for slimes + player  
  - Slimes take damage/die  
  - Player sword attacks: poke, slash, uppercut, heavy slash  
  - ! Tried dash attack → removed (not like i wanted)  

---
### UPDATE 22/8/2025 V2

#### Date: 11/8/2025  
- Improved player sprite  
- Added dynamic chunk loading  
- Added block edges (rendered even with neighbors — buggy)  

---
### UPDATE 22/8/2025 V1

#### Date: 4/8/2025  
- Added isometric renderer + view  
- Added placeholder player sprite (rendered isometric)  
- Added basic movement  
- Made config.js, world.js, isometric.js and player.js