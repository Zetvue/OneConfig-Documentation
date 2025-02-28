---
description: Find out how to create Configs with OneConfig
---

# Creating a Config

## Getting Started

To create a new config, you need to create a brand new class that extends the `Config` class, just like this:

```java
public class MyConfig extends Config {
}
```

Simple! Now, you need to create a constructor for your config, which takes a Mod object, which stores the name, and category of your mod (seen in the GUI later); along with the name of the config file for your mod, which usually is "yourmodname.json".

```java
public MyConfig () {
    // Available mod types: PVP, HUD, UTIL_QOL, HYPIXEL, SKYBLOCK
    super(new Mod("My Mod", ModType.UTIL_QOL), "config.json");
}
```

Also, if you like, you can specify an icon for your mod which is also shown in the GUI. If you have an icon (PNG or SVG), do this instead:

```java
public MyConfig() {
    // Available mod types: PVP, HUD, UTIL_QOL, HYPIXEL, SKYBLOCK
    super(new Mod("My Mod", ModType.UTIL_QOL, "/filepath/to/icon.png"), "config.json");
}
```

Finally, you have to initialize your config when the game launches, Which can easily be done using [Broken link](broken-reference "mention") system and `InitializationEvent`, most commonly in your main class:

```java
public class MyMod {
    public static MyConfig config;

    @Subscribe
    public void onInit(InitializationEvent event) {
        config = new MyConfig();
    }
}
```

That's it! Simple right? Your config is now registered in OneConfig, can be seen in the GUI, so now it's time to start adding options!



## Example Config GUI

Here is an example config GUI, if you are looking for a sneak peek or some inspiration :)

![Example Config GUI for inspiration](<../.gitbook/assets/image (6).png>)
