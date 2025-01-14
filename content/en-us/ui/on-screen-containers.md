---
title: On-Screen UI Containers
description: On-screen UI containers hold GuiObjects that you want to display on a user's screen.
---

**On-screen UI container objects** hold
`Class.GuiObject|GuiObjects`
that you want to display on a user's screen. All on-screen UI objects and code
are stored and changed on the client.

<img src="../assets/ui/container-frames/Frame-Example.jpg" width="800" />

<Alert severity="info">
For UI container objects that hold `Class.GuiObject|GuiObjects` that you want to display within an experience, such as on the face of a part, see <a href="../ui/in-experience-containers.md">In-Experience UI Containers</a>.
</Alert>

## StarterGui

The `Class.StarterGui` service is a container object that holds `Class.GuiObject|GuiObjects`, such as a `Class.ScreenGui` and its children `Class.GuiObject|GuiObjects`. This service initializes on-screen UI for new users joining an experience.
You do not need to create a `Class.StarterGui` object as it is always present in the **Explorer** window.

<img src="../assets/studio/explorer/StarterGui.png" width="320" />

<Alert severity="success">
By default, `Class.GuiObject|GuiObjects` inside a `Class.ScreenGui` within `Class.StarterGui` appear as an overlay of the [3D&nbsp;viewport](../studio/ui-overview.md#3d-viewport), simulating their appearance and position in a running experience. To hide all such screen overlays, toggle off **GUI&nbsp;overlay** from the [Visualization&nbsp;Options](../studio/ui-overview.md#visualization-options) widget in the upper‑right corner of the 3D viewport, or toggle off [UI&nbsp;Visibility](../studio/view-tab.md#ui-visibility) from the [View](../studio/view-tab.md) tab.
</Alert>

<Alert severity="info">
If `Class.Players.CharacterAutoLoads` is disabled, the `Class.GuiObject|GuiObjects` held in `Class.StarterGui` will not be initialized until `Class.Player:LoadCharacter()` is called.
</Alert>

## PlayerGui

`Class.PlayerGui` is a container for on-screen UI objects for a specific `Class.Player`. When a user first joins an experience, the `Class.PlayerGui` automatically inserts into their `Class.Player` object within the `Class.Players` service. Then, when the user's avatar spawns for the first time, the `Class.StarterGui` service clones all of its contents into the `Class.PlayerGui` container.

## ScreenGui

The `Class.ScreenGui` object is the primary container for all 2D `Class.GuiObject|GuiObjects` that display on a user's screen.

### Creating a ScreenGui

Unlike `Class.StarterGui` and `Class.PlayerGui`, you have to manually create a `Class.ScreenGui` to hold anything you want to display on the user's screen. To create a `Class.ScreenGui` object:

1. In the **Explorer** window, hover over **StarterGui** and click the **&CirclePlus;** icon. A contextual menu displays.

2. Insert a **ScreenGui**.

   <img src="../assets/studio/explorer/StarterGui-ScreenGui.png" width="320" />

### Parenting a ScreenGui

Parenting the `Class.ScreenGui` to either the `Class.PlayerGui` or the `Class.StarterGui` service enables you to choose how 2D `Class.GuiObject|GuiObjects` appear to users.

- To show a specific `Class.ScreenGui` to an individual user, parent it to their `Class.PlayerGui`.

- To make a general `Class.ScreenGui` display on every user's screen when they join, parent it to the `Class.StarterGui` service.
