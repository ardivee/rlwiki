---
layout: default
title: Dummy Classes
permalink: /pages/assets/dummy-classes
---
{% assign last_modified_at = "21 Feb, 2020"%}
# Dummy Classes ( V3 )

---

###### Dummy Classes are used as a placeholder for the actual Rocket League Classes, this way we can setup our maps!

#### Dummy Classes V2

###### - If you have installed  Dummy Classes V2, you have to delete 2 files to prevent duplicates.
###### - The files ```AKSoundCue.uc``` and ```AKSoundSource.uc```
###### - They are located in ```UDK/Development/src/TAGame```

---

#### Installation

---

###### - Download the Dummy Classes <a id="download-source" class="btn waves-effect waves-light" href="https://github.com/ardivee/RL-Dummy-Classes-v3/archive/master.zip" target="_blank">***Dummy Classes***<i class="material-icons right">file_download</i></a>

###### - Extract the 4 folders into ```UDK/Development/Src```

###### - Now we need to edit ```DefaultEngine.ini``` which is located in ```UDK/UDKGame/Config```

###### - Copy the lines below

> +EditPackages=AKAudio   
> +EditPackages=ProjectX   
> +EditPackages=TAGame

###### - Place them below these lines in the config ( Could look a bit different for you )

> [UnrealEd.EditorEngine]   
> +EditPackages=CustomGame

###### - So it looks kinda like this, and save the file!

> [UnrealEd.EditorEngine]   
> +EditPackages=CustomGame   
> +EditPackages=AKAudio   
> +EditPackages=ProjectX   
> +EditPackages=TAGame

###### - Open UnrealFrontend ( Located in ```UDK/Binaries``` )

###### - Click on Script > Full Recompile and wait till it's done. You can now close it.

###### - Open UDK and you should now have all the Dummy Classes loaded!

**Last Updated: {{ last_modified_at }}**