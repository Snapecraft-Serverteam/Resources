## Motivation
Needing to start and manage a test server every time you changed something in your plugin is tedious - why not start the server right in your IDE?

**If you want to start a spigot server directly in your IntelliJ IDEA IDE, you just have to follow these steps:**

## Step-by-Step Guide

1) Create your plugin project in IntelliJ (preferably through the Minecraft Development plugin for IntelliJ)
2) Create a new directory in the root folder of your project called "server" (not _in_ the src folder, but on the same layer)
3) Move the spigot server JAR into this folder
4) Click on "Add Configuration..." in the top bar
5) Click on the plus icon in the upper left and choose "JAR Application"
6) Give your Configuration a name, e. g. "Spigot Server"
7) Select your .jar file using the folder icon in the "Path to JAR:" textbox
8) Select your "server" directory you created in step 2 at "Working directory:"
9) If applicable, select a JRE
10) Click Apply and OK, then start your server by clicking the 'play' icon in the top bar (don't forget to accept the EULA in eula.txt)
11) You now can control your server using commands in the Run window at the bottom of your IntelliJ window
12) Enjoy!

## Appendix

This is what the Run/Debug Configurations window looks like for me: <br>
![](https://i.imgur.com/rYVBVyy.png)
