# Arcus-Support-Tutorial
This repo is to help theme engine themers to add support for Arcus in their themes

Introduction
------------

Arcus is an app that allows users to use custom configurations for any theme engine supported theme. We have seen many themes that bundle multiple apks in a single theme/apk to distribute several color variants of the theme. Often such themes have been suspended from the play store by Google. Arcus is specifically developed for this purpose, however, not limited to it.

How it works...
---------------

The way arcus functions currently is quiet simple. It updates the assets/ folder of an apk by replacing with alternative assets/ provided by the themer. Hence, it may be used to update just the colors of an overlay, revamp an overlay or the entire theme itself. YOU name it.

For eg. if a themer wants to provide his theme in 5 different color variations. The best way to do it would be to redirect the main theme colors of each overlay from 'common/res/values/colors.xml'. And since only a single file changes the colors for each color variant, you can prepare a zip of the assets folder with just the changed file(s). 

# Step by step instructions

Step 1: Prepare a zip of assets/ folder with changed file(s)
-------------------------------------------------------------------
You need only the changed files in the zip file with the folder structure intact straight from assets/ folder to the destination file or files. This is because the zip extracts the new assets folder inside it over the assets folder in the base theme thereby replacing the changed files.

> <b>IMPORTANT</b>: The zip file must contain the entire path of the file from its location in assets up to the parent assets folder itself. You will find a method to do this quickly below.

Example: If you direct all theme colors from common/res/values/colors.xml and change this file for preparing color variations, you need only this file in the zip with the folder structure intact. 

This is how I would do it with 7-zip file manager:

1. Change the color values from common/res/values/colors.xml

2. Copy the assets folder of the theme project to the root directory in you hard drive eg. **C:**   or   **D:**

2. Navigate to the changed file (assets/overlays/common/res/values/colors.xml) inside the newly copied assets folder.

3. Right click the changed file (colors.xml) and select 7-Zip>Add to archive
![alt tag](https://dl.dropboxusercontent.com/u/35007332/Arcus/Github/1.png)

4. In the subsequent dialog prepare the zip with the below parameters. 
![alt tag](https://dl.dropboxusercontent.com/u/35007332/Arcus/Github/2.png)
> **NOTE**: The zip name is the config id for arcus to identify the zip. Choose a  short unique name for the zip with NO spaces, special charaters (except underscore, "_") or capital letters. Eg. Prozt - Pink variant config zip can be named as prozt_pink.zip
4. DONE. 
   

Step 2: Changes to your theme's src/main/res folder
-------------------------------------------------------
Sample res/ folder is uploaded to this project for your reference. Study the below steps by referring to this folder.

----------------------------------------------------------------------------
**1** Copy the prepared config zip to **res/raw** folder of your theme

----------------------------------------------------------------------------
**2.** **Place config preview image**

![alt tag](https://dl.dropboxusercontent.com/u/35007332/Arcus/Github/preview_image.png "Screenshot of a preview image")
> **Location**: res/drawable-nodpi/
> 
> **Dimensions**: Themer's choice (Recommended: 1024w x 500h px)
> 
> **File size**: Try to limit its size to below 150 kb. Use TinyPNG (Recommended) or PNG Gauntlet.
> 
> **File name**:  MUST be same as the config zip name
> 
> **Example**: For config **prozt_pink**  		preview image MUST be **prozt_pink**.jpg (or **prozt_pink**.png)

----------------------------------------------------------------------------
**3.** **Place config screenshots**
> **Dimensions**: Standard screenshot dimensions from your devices or test your own.
> 
> **File size**: Optimize the screenshots (if required). Use TinyPNG (Recommended) or PNG Gauntlet.
> 
> **File name**: Naming convention is mandatory as below: config-name_screen1, config-name_screen2 and so on
> 				
> **Example**: For config: **prozt_pink**  Screenshots MUST be named as: prozt_pink_screen1, prozt_pink_screen2 and so on

----------------------------------------------------------------------------
**3.** **Place XMLs in values/ folder**

Two xml files are to be maintained:

>  - arcus_configs_array.xml
> 	 - This file contains an arrray list of the configs' names i.e. zip names without the '.zip' suffix
>  - arcus_configs_details.xml
> 	 - This file contains details of each config such as actual name to be displayed, version, no. of screenshots

Have a look at these files. Instructions on how to use them is within the files.

Step 3: Add a meta-data tag in the theme's AndroidManifest
-----------------------------------------------------------------

This lets Arcus know that the theme supports it and has custom assets zips ('configs' from now on).

Include the tag:  
`<meta-data android:name="arcus.support" android:value="true"/>`

as shown below:

    <application
        android:hasCode="false"
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:theme="@style/AppTheme">
        <meta-data android:name="arcus.support" android:value="true"/>
    </application>