## Motivation
Creating banners for Minecraft is quite easy nowadays - but how can you transfer your design to an `ItemStack` in Spigot?
In the Appendix, you'll find some example banners.

## Guide
First, choose a banner design from planet minecraft. Generate a command for it and open this reddit post in a second tab:<br>
[https://www.reddit.com/r/Minecraft/comments/2bhz8o/banner_nbt_a_quick_guide/](https://www.reddit.com/r/Minecraft/comments/2bhz8o/banner_nbt_a_quick_guide/) <br>

Prepare this codebase:
```java
            ItemStack i = new ItemStack(Material.BANNER, 1); //create an itemstack
            BannerMeta bannerMeta = (BannerMeta)i.getItemMeta(); //get the meta of your banner

            bannerMeta.setBaseColor(DyeColor.BLACK); // set the background color of your banner

            List<Pattern> patterns = new ArrayList<Pattern>(); // create a list where we'll add some patterns

            // Add your patterns here
            // example: patterns.add(new Pattern(DyeColor.WHITE, PatternType.RHOMBUS_MIDDLE));
            // ...
            
            bannerMeta.setPatterns(patterns); // set the list of patterns
            bannerMeta.addItemFlags(ItemFlag.HIDE_POTION_EFFECTS); //somehow does this hide the banner pattern lore
            bannerMeta.setDisplayName("My Banner"); // Set a display name for the banner
            i.setItemMeta(bannerMeta); //save your changes to the meta
```

Look what pattern codes are used in the generated command (the one from planet minecraft) and look up the name in the reddit post. The spigot names for the banners are a bit off the vanilla names, so make sure to "search" for keywords with the help of your IDE (CTRL+SPACE for IntelliJ).
As described in the comments of the snippet above, add each pattern to the list `patterns`

## Appendix
Here's a collection of some banners:
### Arrow pointing left
```java
ItemStack i = new ItemStack(Material.BANNER, 1);
            BannerMeta bannerMeta = (BannerMeta)i.getItemMeta();

            bannerMeta.setBaseColor(DyeColor.BLACK);

            List<Pattern> patterns = new ArrayList<Pattern>();

            patterns.add(new Pattern(DyeColor.WHITE, PatternType.RHOMBUS_MIDDLE));
            patterns.add(new Pattern(DyeColor.WHITE, PatternType.HALF_VERTICAL));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.SQUARE_BOTTOM_LEFT));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.SQUARE_TOP_LEFT));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.TRIANGLES_BOTTOM));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.TRIANGLES_TOP));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.BORDER));
            bannerMeta.setPatterns(patterns);
            bannerMeta.addItemFlags(ItemFlag.HIDE_POTION_EFFECTS); //somehow does this hide the banner pattern lore
            bannerMeta.setDisplayName("§bNächste Seite");
            i.setItemMeta(bannerMeta);
```
### Arrow pointing right
```java
ItemStack i = new ItemStack(Material.BANNER, 1);
            BannerMeta bannerMeta = (BannerMeta)i.getItemMeta();

            bannerMeta.setBaseColor(DyeColor.BLACK);

            List<Pattern> patterns = new ArrayList<Pattern>();

            patterns.add(new Pattern(DyeColor.WHITE, PatternType.RHOMBUS_MIDDLE));
            patterns.add(new Pattern(DyeColor.WHITE, PatternType.HALF_VERTICAL_MIRROR));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.SQUARE_BOTTOM_RIGHT));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.SQUARE_TOP_RIGHT));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.TRIANGLES_BOTTOM));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.TRIANGLES_TOP));
            patterns.add(new Pattern(DyeColor.BLACK, PatternType.BORDER));
            bannerMeta.setPatterns(patterns);
            bannerMeta.addItemFlags(ItemFlag.HIDE_POTION_EFFECTS); //somehow does this hide the banner pattern lore
            bannerMeta.setDisplayName("§bVorherige Seite");
            i.setItemMeta(bannerMeta);
```
