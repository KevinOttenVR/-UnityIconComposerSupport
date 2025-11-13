# Unity iOS / iPadOS Icon Composer Support
Automatically integrates Apple Icon Composer .icon bundles into Unity iOS/iPadOS builds (Xcode 26+), including automatic App Icon assignment.

This removes the need to manually drag your app icon into Xcode after every rebuild.

# What this script does
- Detects a `.icon` bundle exported from Apple Icon Composer
- Copies it into the root of the generated Xcode project
- Adds it to the Xcode project automatically
- Assigns it as the App Icon  
  (`CFBundleIconName` + `ASSETCATALOG_COMPILER_APPICON_NAME`)
- Removes Unity’s default icon metadata to avoid conflicts

No manual Xcode steps. No re-assigning icons.
Just build → open Xcode → run.

## Installation

1. Within your Unity project, create a folder (if not yet present):  
   `Assets/Editor/`

2. Add the script  
   Place `IOSIconComposerIcon.cs` inside `Editor` folder.

3. Within you Unity project create another folder:  
   `Assets/AppIcon/`

4. Export your icon from Apple Icon Composer  
   Save the `.icon` file and move it into the `AppIcon` folder.

5. Build for iOS/iPadOS  
   Unity will generate an Xcode project with your icon already assigned, including automatically setting the App Icon name based on the `.icon` file.

That’s it! No additional configuration required.

## Notes

- Unity 2019.3 or newer (tested on Unity 6 / 6000.x)
- Xcode 26 or newer
- The script uses the **first** `.icon` bundle it finds in `Assets/AppIcon/`
- Unity may show the `.icon` as a folder in the Project view – that’s expected
