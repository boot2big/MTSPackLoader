Before we start, you're going to need a fancy text editor that features a "find-and-replace across every file" function, otherwise you'll need to manually search for several lines that you will need to change! Absolutely no Notepad beyond this point! (Notepad++, Gnome Text Editor, JEdit, Eclipse, etc. will suffice.)  
  
HOW TO USE  
  
Step 1. Place all of your assets into their appropriate folders depending on their use-case. Generally you will want to put them into `/mccore/src/main/resources` as this will ensure that your assets are copied into both versions of your pack, however you may find the need to have specific JSONs, textures, et cetera specifically confined to 1.12.2 or 1.16.5, in which case they will go to `/mcinterfaceforge1122/src/main/resources` and `/mcinterfaceforge1165/src/main/resources` respectively.  
Once you've put your pack's assets into their appropriate locations, don't forget to remove the placeholder files! (`version-agnostic-assets-go-here`,`1122-specific-assets-go-here`,`1165-specific-assets-go-here`) There are no consequences for not doing this, but there's no reason to keep them there either...

Step 2. Replace all instances of `examplepack` with your pack's shortform ID (see examples) and replace all instances of `Example Pack` with your pack's fancy name! This is where the fancy F&RAEF feature of your fancy text editor comes in, otherwise you will need to manually edit each of these by hand. (see imgur link)  
Examples of shortform IDs: mtsofficialpack, iv_tcp_v3, ivv, unucivil  
Examples of fancy names: MTS Official Content Pack, Immersive Vehicles Trin Civil Pack, Immersive Vehicles Vanity, UNU Civil Pack  
Locations of `examplepack` and `Example Pack` https://imgur.com/a/18qsLvj  

Step 3. Rename the folders in `/mcinterfaceforge1122/src/main/java/` and `/mcinterfaceforge1165/src/main/java/` from `examplepack` to the shortform ID of your pack.

Step 4. Open up a Command Line or Terminal (platform dependent, CMD and gradlew.bat for Windows VS bash and ./gradlew for Linux) and navigate to the root folder of this repository.  
Run `gradlew clean` to allow the compiler to prepare itself (only on the first time you run it) and clean up things. This helps to prevent ghost directories, outdated files and is generally a good idea to my knowledge.  
Then simply run `gradlew buildForgeAll` to build both the 1.12.2 and 1.16.5 versions of your pack, which will be located in the `/out` directory.

In four easy steps you have now upgraded your pack to 1.16.5! All you need to do for subsequent updates is to modify your assets as usual (whether they're in `/mccore` or otherwise) and simply `clean` & `buildForgeAll` a second time!
