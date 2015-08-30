# Arcus-Support-Tutorial
This repo is to help theme engine themers to add support for Arcus to their themes

# Introduction
Arcus is an app that allows users to use custom configurations for any theme engine supported theme. We have seen many themes that bundle multiple apks in a single theme/apk to distribute several color variations of the theme. Often such themes have been suspended from the play store by Google. Arcus is specifically developed for this purpose, however, not limited to it.

# How it works...
The way arcus functions currently is quiet simple. It updates the assets/ folder of an apk by replacing with alternative assets/ provided by the themer. Hence, it may be used to update just the colors of an overlay, revamp an overlay or the entire theme itself. YOU name it.

For eg. if a themer wants to provide his theme in 5 different color variations. The best way to do it would be to redirect the main theme colors from 'common/colors.xml'. And since only this file changes the entire theme colors, you can prepare a zip of the assets folder with just the changed file. IMPORTANT: The zip file must contain the entire path of the file from its location in assets to the assets folder itself. You will find a method to do this quickly below.
