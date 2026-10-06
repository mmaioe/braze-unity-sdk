<p align="center">
  <img width="480" alt="Braze Logo" src=".github/assets/logo-light.png#gh-light-mode-only" />
  <img width="480" alt="Braze Logo" src=".github/assets/logo-dark.png#gh-dark-mode-only" />
</p>

# Changes from the original Braze Unity SDK

This branch is an example where we added delayed initialization for Android Platform.

1. execute [AppboyUnityManager prepareForDelayedInitialization]; in AppboyAppDelegate.m in stead of executing normal SDK initialization.
   → This is added for enabling Delayed initialization

2. added "InitBrazeAfterDelayedInitialization" functionality
   → This is for calling disableDelayedInitialization, i.e. execute SDK initialization.

The corresponding braze document is https://www.braze.com/docs/developer_guide/sdk_integration#android_step-43-manually-initialize-the-sdk

You can search InitBrazeAfterDelayedInitialization in this repository's file to see what kind of changes I have made.

3. Now, you can call Appboy.AppboyBinding.InitBrazeAfterDelayedInitialization(); in Unity to complete SDK initialization when you want to.



Braze Unity SDK
==========

This repository contains the the C# interface and native Unity functionality for the Unity plugins derived from the Braze Android and iOS SDKs. Since version 1.5.0, Braze's Unity plugins require Unity 5. See the CHANGELOG for more information.

## Plugin Setup

Before you can start using Braze in Unity scripts, you'll need to import the plugin files to your Unity project.

**Recommended:** The Android and iOS plugins are bundled as a Unity package available for download from the [SDK release page][1].

**Manual Plugin Setup:** Alternatively, you can copy the plugins into your Unity project:
  1. First, clone this repo.
  2. If you're not using any other plugins, all you have to do is copy the `Plugins` directory from this repo into the `Assets` folder of your Unity project.
  3. If you already have a `/<your-project>/Assets/Plugins` directory (probably because you're using another plugin already), copy `Plugins/Appboy/AppboyBinding.cs` into `/<your-project>/Assets/Plugins`. Then copy the contents of `Plugins/iOS` and `Plugins/Android` from this repo into `/<your-project>/Assets/Plugins/iOS` and `/<your-project>/Assets/Plugins/Android` respectively.

## Integration Setup

To integrate Braze into your Unity application, complete our instructions for [Integrating the Braze Unity SDK][2].

[1]: https://github.com/braze-inc/braze-unity-sdk/releases
[2]: https://www.braze.com/docs/developer_guide/platforms/unity/sdk_integration
