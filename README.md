# Arcus-Support-Tutorial
This repo is to help theme engine themers to add support for Arcus in their themes

Introduction
------------

Arcus is an app that allows users to use custom configurations (referred as configs from here) for any theme engine supported theme. We have seen many themes that bundle multiple apks in a single theme/apk to distribute several color variants of the theme. Arcus is specifically developed for this purpose, however, not limited to it (Read below to learn more).

How it works
---------------

The way arcus functions currently is quiet simple. It extracts the assets of a theme and replaces it with alternative assets/ provided by the themer. Hence, it may be used to update just the colors of an overlay, revamp an overlay or the entire theme itself. YOU name it. (Note that a new theme apk is prepared with the updated assets and the old base theme remains unaffected).

For eg. if a themer wants to provide his theme in 5 different color variations. The best way to do it would be to redirect the main theme colors of each overlay from 'common/res/values/colors.xml'. And since only a single file changes the colors for each color variant, you can prepare a zip of the assets folder with just the changed file(s). 

How to add arcus support to your theme
---------------
Refer the [Wiki](https://github.com/dchris87/Arcus-Support-Tutorial/wiki) for a step by step guide.
