---
description: >-
  Learn about the button, color and keybind elements that can be used in a
  config.
---

# Buttons, Colors and Keybinds

## Button

A button is a simple call-to-action button that can be used to invoke some code when it is pressed by the user. It has dual and single column variants.

You can create your method to run when the button is pressed using the Runnable interface:

```java
@Button(
    name = "I'm a button",    // name beside the button
    text = "Click me!"        // text on the button itself
)
Runnable runnable = () -> {    // using lambda to create the runnable interface.
    System.out.println("I was clicked!");
    FMLCommonHandler.instance().exitJava(69, false);
}
```

![Buttons with single and dual variant examples](<../../.gitbook/assets/image (5).png>)

## Colors

Color config elements are probably the most popular config elements available. They show the alpha, hex and a preview of the color, and when the preview is double clicked it opens up the color picker. It also has dual and single column variants.

The color picker has a color wheel, color box, and Chroma picker; along with support for favorites, and recent colors. See the pictures below for more.

```java
@Color(
    name = "Background Color"
)
OneColor testColor = new OneColor(26, 35, 143);        // default color
```

{% hint style="success" %}
This config component uses [onecolor.md](../../utils/onecolor.md "mention") to store the colors.
{% endhint %}

![Color examples, single and dual column](<../../.gitbook/assets/image (12).png>)

![Color selector GUI examples](<../../.gitbook/assets/image (15).png>)

## Keybinds

OneConfig also has keybind elements that can be displayed as configs. They replace the Minecraft keybind system, and use much more multiplatform methods to process key presses. See [onekeybind.md](../../utils/onekeybind.md "mention") for more information.\
It, similarly, has dual and single column variants.

{% hint style="success" %}
This config component uses [onekeybind.md](../../utils/onekeybind.md "mention") to store the keybinds.
{% endhint %}

```java
@KeyBind(
    name = "I'm a keybind!"
)
// using OneKeyBind to set the default key combo to Shift+S
public static OneKeyBind keyBind = new OneKeyBind(UKeyboard.KEY_LSHIFT, UKeyboard.KEY_S);
```

![Keybind field examples, including recording state](<../../.gitbook/assets/image (19).png>)
