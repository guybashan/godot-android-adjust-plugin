# Godot Android Adjust Plugin
This is Android Adjust plugin for Godot 3.2.2 or higher.

## How to use
* On your Godot project install android build template. You can follow the [official documentation](https://docs.godotengine.org/en/latest/getting_started/workflow/export/android_custom_build.html)
* Go to Releases (on the right of this repository page) and download a released version. It is a ZIP file containing 2 files: "aar" of the plugin and "gdap" file describing it,
* Extract the contents of the released ZIP file to res://android/plugins directory of your Godot project
* On Godot platform choose: Project -> Export -> Options and make sure turn on the "Use Custom Build" and "Godot Adjust" on the "Plugins" section:
![Annotation 2020-07-24 213436](https://user-images.githubusercontent.com/3739222/88424072-9644e300-cdf5-11ea-9a1d-9d282b70550e.png)

## Basic Example in Godot (GDScript)
*Recommended: Load the following as a singleton*
```
extends Node

const adjust_app_token = "yyzasoa5g2yo"
const adjust_production = false

var adjust
func _ready():
	if (Engine.has_singleton("GodotAdjust")):
		print("Adjust was detected")
		adjust = Engine.get_singleton("GodotAdjust")
		adjust.init(adjust_app_token, adjust_production)
	else:
		print("Adjust was not detected")
```

## Api Reference

**Functions:**
```
init(app_token, production)
* app_token - Your adjust app token.
* production - If true, run adjust in production mode. Else, use sandbox mode.
```
