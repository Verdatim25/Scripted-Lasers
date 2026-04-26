# Scripted-Lasers
Scripted Lasers Mod For Stalker GAMMA

WILL PROBABLY BE REPLACED BY ANOMALY 1.6 AND ITS SCRIPTED MODULAR ATTACHMENT SYSTEM! (but who knows when thats coming out. You can use this for now I guess.)  

Enables Scripted Lasers for weapons, attachable separate from scopes. Saves laser attachment via se_save_var to bind to the object.  
Adds Lasers to NATO traders from lvl 1 (second level // 500 rep) and WP traders from lvl 2 (third level // 1000 rep).  
Places an icon layer of the laser on the weapon, looks a little cursed for now sorry.  
Attachable lasers can be seen in the details tab of the weapon and are highlighted when the weapon is hovered.  
Unforunately I cant put it on too many weapons because many guns in GAMMA that have side rails already have lasers on by default.

## CREDITS: 
Demonized for his item details script  
Raven for his icon layers script  
Haruka for the bas laser toggle script (which i monkey patched)  
BAS team? for the laser models (i dont remember where i got them).  
You. for being the reason i make stuff!  

## INSTALLATION:  
Install this mod via MO2, ideally put at end of load order, but it shouldn't matter. Made ONLY for GAMMA. I'll eventually make a dependencies list of mods for other modpacks / personal modlists.

## REMOVING THIS MOD:  
Since this mod adds new items and saves variables to items, you will need to use the item despawner script in the "gamedata//scripts//remove_items": called "remove_scripted_lasers.script"  
Simply move this script from the "remove_items" folder into the main "scripts" folder and launch the game. Then enter your save and press the save button (F5 by default), you should then receive a message telling you how many items and variables were removed. Then you can deactivate the mod in MO2 and use the new save file that you got from saving earlier to continue playing the game.  

## FOR MODDING:  
Turning on DEBUG in the MCM allows you to change the position, rotation and scale of the lasers and allows you to put any laser on any gun (for testing purposes) 

### KEYBINDS:  
Here are the base keybinds (all configurable by MCM; also sorry i couldnt make a menu for this im too lazy):  
keys.xup = DIK_keys.DIK_NUMPAD1 (Increases x pos or rot, depending on mode)  
keys.yup = DIK_keys.DIK_NUMPAD2 (Increases y pos or rot, depending on mode)  
keys.zup = DIK_keys.DIK_NUMPAD3 (Increases z pos or rot, depending on mode)  
keys.xdown = DIK_keys.DIK_NUMPAD4 (Decreases x pos or rot, depending on mode)  
keys.ydown = DIK_keys.DIK_NUMPAD5 (Decreases y pos or rot, depending on mode)  
keys.zdown = DIK_keys.DIK_NUMPAD6 (Decreases z pos or rot, depending on mode)  
keys.mode_swap = DIK_keys.DIK_ADD (Changes mode from position editing to rotation editing or vice versa.)  
keys.scaleup = DIK_keys.DIK_MULTIPLY (Increases Scale)  
keys.scaledown = DIK_keys.DIK_DIVIDE (Decreases Scale)  
keys.precision_mode = DIK_keys.DIK_DECIMAL (Toggles extra precision to the position, rotation and scale adjustments.)  
keys.reset = DIK_keys.DIK_NUMPAD8 (resets all variables to be 0, i.e. the scripted laser will have the same position and rotation as the root bone of the weapon.)  
keys.swap_model = DIK_keys.DIK_SUBTRACT (changes the PEQ-15 to the blue LAM and vice versa, any new models will not work with this yet.)  
keys.save = DIK_keys.DIK_RSHIFT (Saves the current values of pos, rot, and scale to a temporary cache.)  
keys.copy = DIK_keys.DIK_RETURN (Copies the values of pos, rot, and scale from the temporary cache to the current weapon.)  
keys.save_ltx = DIK_keys.DIK_NUMPAD9 (Saves the current weapons section settings to "mod_system_ver_laser_script_cache.ltx" in the configs folder, remember to reload system.ltx / reload the game to have the new settings apply.)  
keys.display_variables = DIK_keys.DIK_RCONTROL (Displays the current pos, rot, and scale values of the current weapon)  
keys.reset_to_section = DIK_keys.DIK_BACKSLASH (Resets the current pos, rot, and scale values to the ones defined in the weapon section, if it cant find anything it resets to 0)  

### ADDING NEW LASER MODELS
Follow what i have done for the lasers in "mod_system_ver_laser_items.ltx". Firstly, change the "attachment_icon_layer" to a 64x64 dds containing only the LAM you want, this is the icon layer shown on the weapon. Secondly, change the "scripted_model" to the model of your laser. Try your best to match the rail size and rail position to the two already made lasers so it fits nicely. Thirdly, change the cost and icons_texture (icon shown in inventory ui) to whatever you want. Finally, add it to the trader profiles by editing the presets in "gamedata\configs\items\trade\presets". "wp_lasers_preset.ltx" for WP traders and "nato_lasers_preset.ltx" for NATO traders.

### ADDING NEW LASERS TO WEAPONS
Firstly, turn on debug mode via the mcm. This should allow you to add any laser to any weapon regardless of its "scripted_lasers" field. Then add the desired laser onto the weapon of your choice. This should spawn the laser roughly in the middle of the model (the root bone) or in the values defined by its section if those values exists. Then adjust using the keybinds above until its in the position you want it to be in. Then finally press the "save_ltx" keybind (numpad 9 by default) and this should add your weapon section, parameters and ALL lasers of the "scripted_lasers" field of the weapon section to the "mod_system_ver_laser_script_cache.ltx" in your configs folder. If you want to remove a laser's ability to be attached, make sure to go to "mod_system_ver_laser_script_cache.ltx" and remove that laser's section from the field "scripted_lasers" for your weapon section. Also if you want to you can move these DLTX changes to another "mod_system_*.ltx".

## CHANGELOG:  
0.1 -- First release  
0.1.1 -- Lowered costs of Lasers: PEQ15 from 40000 to 15000 and Blue LAM from 40000 to 20000  

## TO DO:  
Add new lasers  
Make lasers affect weapon stats  
Maybe make an attachable rail system? might be too hard  
Allow moving the lasers along the rail without debug (looks cool)  
Save the position of the attachment to the object variable if i do try to make the position customisable without debug  
Allow different attachment points to move the laser to and fro  
