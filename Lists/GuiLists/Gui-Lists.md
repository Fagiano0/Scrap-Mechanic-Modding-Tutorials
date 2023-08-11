---
title: "Gui Lists | SMMT"
---

[← Back](/index.md)

# Gui Lists
*Written by [The Red Builder](https://github.com/TheRedBuilder) with contributions from [Fagiano0](https://github.com/Fagiano0)*  
This list contains most gui things.

### CONTENTS:
- [Widget Types](Gui-Lists#widget-types)
- [Lua Widget Types](Gui-Lists#lua-widget-types)
- [Fonts](Gui-Lists#fonts)

## Widget Types
This list contains every widget available in Scrap Mechanic and its function.
- Button 
	- An interactive Widget  
	- Button skins have 3 different states:
		- Inactive
		- Highlighted
		- Active
- Canvas
	- Empty widget
	- Can be used for rendering Mesh Previews
- ComboBox
	- Gives you a dropdown box with rewriteable text options  
	![ItemsInterface](Images/AddItems.png "Items Interface")
- DDContainer
	- *Possibly Drag & Drop container?*
	> ***Note**: Doesnt work yet.*
- EditBox
	- Fancier version of TextBox
	- Supports better formatting and multiline
	- Text can be edited ingame, unless ReadOnly  
	![ReadOnlyOption](Images/ReadOnly.png "ReadOnly Option")
- ItemBox
	- *Possibly related to Drag & Drop container?*
	> ***Note**: Doesnt work yet.*
- ListBox
	- Lists all Items properties.  
	![ItemsInterface](Images/AddItems.png "Items Interface")
- MenuBar
	- Automatically creates buttons from its Item property
	> ***Note**: Very limiting, lacks any SM-like skins. Mostly useless*
- MenuListBox
	- *???*
- PopupMenu
	- Automatically creates buttons from its Item property and adjusts its scale
	- Clicking any option makes it disappear
- ProgressBar
	- Visualizes progression
	- AutoTrack option works in Scrap Mechanic and makes it track infinitely  
	![ProgressBarInterface](Images/ProgressBar.png "ProgressBar Interface")
	> ***Note**: You can't interact with it through lua.*
- ScrollBar
	- Lets you scroll in its range  
	> ***Note**: You can only set its callback through lua.*
- ScrollView
	- Adds 2 Scrollbars, that let you move around its own viewport
		- To set its size, use CanvasSize
		> ***Note**: CanvasSize is in Pixels only*
- ImageBox
	- Can be used to display tiled images
- TextBox
	- Basic textbox
	> ***Note**: More limiting than EditBox*
- TabControl
	- Widget with multiple tabs that player can switch between
	- Can have different widgets on every page
	- Pages are added from the Items property  
	![ItemsInterface](Images/AddItems.png "Items Interface")
- Widget
	- Dummy Widget that only shows its Skin
- Window
	- Dragabble window that can be resized, depending on the skin
	> ***Note**: Only scales its viewport.*
	
## Lua Widget Types
Contains every Widget that must be created with Lua.
- Lua Dropdown
	- Works similarily to ListBox Widget, but better
	- Creation:
	```lua
	self.gui:createDropDown("DropdownHost", "cl_myFunction", {"Option1","Option2"}) -- change self.gui to your created gui, change "DropdownHost" to the name of your Widget (Widget should be empty, with panelEmpty skin), change "cl_myFunction" to the name of the function that will receive its callback, fill in the table {"Option1","Option2"} with the option names, these are returned to the callback when player clicks them.
	```
- Lua Sliders
	- Similar to ScrollBar Widget, but with improved functionality, at the cost of more skins
	- Creation:
	```lua
		--[[
			change "SliderHost" to the name of your Widget (should be empty, with panelEmpty skin)
			change "cl_myFunction" to the name of the function that will receive its callback
			change the first number (100) to the maximal value of the slider
			change the other number (50) to its starting value
		]]

		-- for horizontal slider:
		-- the boolean (true) controls if it should be numbered (exclusive to horiziontal)
		guiInterface:createHorizontalSlider("SliderHost", 100, 50, "cl_myFunction", true)
		
		
		-- for vertical slider:
		guiInterface:createVerticalSlider("SliderHost", 100, 50, "cl_myFunction")
	```

## Fonts
All the fonts available including their supported characters.

- All Characters
	- Default
	- SM_HeaderLarge_Medium
	- SM_HeaderTiny
	- SM_Button
	- SM_SubHeader
	- SM_Tab
	- SM_TabSmall
	- SM_ItemTitle
	- SM_TextTiny
	- SM_TextSmall
	- SM_Text
	- SM_UserName
	- SM_SearchText
	- SM_ToolTipText
	- SM_ButtonSmallBold
	- SM_ListItem
	- SM_HotbarBinding
	- SM_GameName
	- X_Hud_PlayerName
	- X_Hud_Interaction
	- X_Hud_Alert
	- X_Interactable_LogicGate_Category
	- SM_IntlText
	- SM_TextLabel
	- SM_Label
	- SM_LabelSmall
	- SM_LabelTiny
	- SM_ButtonTiny
	- SM_NumberTiny
	- DejaVuSansFontGenerated_13
	- DejaVuSansFontGenerated_15
	- DejaVuSansFontGenerated_28
- Only Numbers
	- SM_LabelMini
	- SM_SliderLabel
	- X_Hud_ItemStack
- Other
	- SM_Digital: `0123456789:`
	- SM_NumberHuge: `0123456789:`
	- SM_NumberMini: `0123456789*`
	- SM_NumberSmall: `aAbBcCDeEfFGhHiIkKlLmMnNoOpPrRsStTuUvVwWXYZ0123456789-[]:!`
	- HandbookPageCount: `0123456789/`
	- SM_ButtonLarge: `ABCEFGHIKLMNOPRSTUX`
	- SM_Header: `aAbBcCdDeEfFgGhHiIJkKlLmMnNoOpPrRsStTuUvVwWxXyYZ0123456789/.!_?`
	- SM_HeaderSmall: `aAbBcCDeEfFGhHiIkKlLmMnNoOpPrRsStTuUvVwWXYZ0123456789-[]:!`
	- SM_HeaderMedium: `ABCDEGHILMNORSTUWY`
	- SM_HeaderLarge_Narrow: `aAbBcCdDeEfFgGhHiIJkKlLmMnNoOpPrRsStTuUvVwWxXyYZ0123456789/_\.,?!`
	- SM_HeaderLarge_Wide: `aAbBcCdDeEfFgGhHiIJkKlLmMnNoOpPrRsStTuUvVwWxXyYZ0123456789/_\.,?!`
	- SM_HeaderXLarge_Wide: `ADEFIMNOPRSTUV`
	- SM_TextLarge: `aAbBcCdDefFgGhijJklmMnopQrsStTuUvwyYzZ+.:,!`
	- HandbookTitle: `ABCDEFGHILMNOPQRSTUVWY`
	- HandbookSubTitle: `aAbBcCdeEfFghHiIjklLmMnNopPqQrRsStTuUvwWxyYz35+-().,?`
	- HandbookSubTitleItalic: `abcdeEfghiklLmnoprstTuvwxy.,!`
	- HandbookDescriptionLarge: `aAbBcCdefghiIklmnopPqrsStTuvwyz.,`
	- HandbookDescriptionSmall: `aAbBcCdefFghHijklmnopPqQrsStTuUvwWxyYz-.:,!`
	- HandbooInstructionSmall: `aAbBcCdDefghHijkKlLmnopPrRsStTuwWy`
	- HandbookInstructionMedium: `aAbcCdDeghHiIjJklLmMnoOpPrRsStuv`
	- HandbookInstructionLarge: `abBcCeHiIklmnoPrstuvy`
	- HandbookLogicDescription: `aAcdefghiklnorstvy`
	- HandbookFAQQuestion: `abcdefghHiIlmMnoOprstuvwWy,?!`
	- HandbookFAQAnswer: `aAbBcCdeEfFghHiIjklLmMnNopPqQrRsStTuUvwWxyYz35+-().,?`
	- X_Interactable_Timer_TickCount: `CIKST0123456789`
	- X_Interactable_Timer_TimeUnit: `MS`
	- X_MenuGamemodeMenu_GameMode: `ACEGHILNRSTUV`
	