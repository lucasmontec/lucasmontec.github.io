---
name: Quick Templates
type: Tool

font_awesome_icon: fa-gavel

one_liner: Quick Templates creates context menus for your most used prefabs.

direct_link: https://assetstore.unity.com/packages/tools/utilities/design-variables-134873

main_image: /assets/images/quicktemplates.webp

---

## Overview

Quick Templates is an editor plugin that facilitates working with prefabs. This plugin creates context menus for your most used prefabs, organizes them in a searchable template manager window, and protects your prefabs from being deleted if they are used in templates.

With Quick Templates, you can speed up your workflow not having to search through thousands of prefabs. Instead, you can quickly create prefab menus with no unity editor code. Just right-click a prefab, a game object on a scene, or any prefab asset on the project view, select Quick Templates and click Create Template. Then adjust your settings, wait for script compilation, and... that's it! Now when you right-click your hierarchy view, there will be a templates option with all of your templates there! Clicking the template menu will create an instance of the current template prefab and it will set it up according to what you prepared for that template.

Templates created through Quick Templates are automatically placed under what you right-clicked on the hierarchy. This ensures that you'll get the Unity workflow that you are accustomed to.

## Why

When working with big game teams and with designers I realised that people spent a lot of time making custom tools to keep their setup aligned. This means creating tools that allow the project to define how the Unity Editor should create the game components they use frequently.

I saw many different instances of these. Some would inject code into the editor and change the behavior of the default context menu. Some would create extra menu entries for their game's UI and objects. Some had custom windows to drag prefabs from. Lots of different setups. All somewhat confusing and not dedicated to the problem, just a quick solution that handled it.

So, with Quick Templates, I created a more streamlined version of this workflow, where devs/designers/PMs/anyone can create their context menus without code, to instantiate any game object as a prefab. I called these prefabs+context menus "templates" and added a window to manage them. This allows devs to replace the prefab, delete the template or simply to consult what is available. All templates generate context menus in a different place than the Create sub-menu, which makes it more explicit that they are using game customized objects.
