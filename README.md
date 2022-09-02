<p align="center"><br><img src="https://avatars.githubusercontent.com/u/105555861" width="128" height="128" /></p>
<h3 align="center">Android Battery Optimization</h3>
<p align="center"><strong><code>@capawesome-team/capacitor-android-battery-optimization</code></strong></p>
<p align="center">
   Capacitor plugin to access battery optimization settings on Android. 
</p>

<p align="center">
  <img src="https://img.shields.io/maintenance/yes/2022?style=flat-square" />
  <!-- <a href="https://github.com/capawesome-team/capacitor-android-battery-optimization/actions?query=workflow%3A%22CI%22"><img src="https://img.shields.io/github/workflow/status/capawesome-team/capacitor-android-battery-optimization/CI/main?style=flat-square" /></a> -->
  <a href="https://github.com/capawesome-team/capacitor-android-battery-optimization"><img src="https://img.shields.io/github/license/capawesome-team/capacitor-android-battery-optimization?style=flat-square" /></a>
<!-- <br> -->
  <!-- <a href="https://www.npmjs.com/package/@capawesome-team/capacitor-android-battery-optimization"><img src="https://img.shields.io/npm/dw/@capawesome-team/capacitor-android-battery-optimization?style=flat-square" /></a> -->
  <!-- <a href="https://www.npmjs.com/package/@capawesome-team/capacitor-android-battery-optimization"><img src="https://img.shields.io/npm/v/@capawesome-team/capacitor-android-battery-optimization?style=flat-square" /></a> -->
  <a href="https://github.com/capawesome-team"><img src="https://img.shields.io/badge/part%20of-capawesome-%234f46e5?style=flat-square" /></a>
</p>

## Maintainers

| Maintainer | GitHub                                    | Social                                        |
| ---------- | ----------------------------------------- | --------------------------------------------- |
| Robin Genz | [robingenz](https://github.com/robingenz) | [@robin_genz](https://twitter.com/robin_genz) |

## Sponsorware

This project is available as **Sponsorware**.

> Sponsorware is a release strategy for open-source software that enables developers to be compensated for their open-source work with fewer downsides than traditional open-source funding models. ([Source](https://github.com/sponsorware/docs))

This means...

- The source code will be published as soon as [our GitHub Sponsors goal](https://github.com/sponsors/capawesome-team) is reached.
- Any GitHub sponsor with a [sponsorware tier](https://github.com/sponsors/capawesome-team?frequency=recurring) gets **immediate access** to our sponsors-only repository and can start using the project right away.

## Terms

This project is licensed under the terms of the MIT license.  
However, we kindly ask you to respect our **fair use policy**:

- Please **don't distribute the source code** of the sponsors-only repository. You may freely use it for public, private or commercial projects, privately fork or mirror it, but please don't make the source code public, as it would counteract the sponsorware strategy.
- If you cancel your subscription, you're automatically removed as a collaborator and will miss out on all future updates. However, **you may use the latest version that's available to you as long as you like**.

## Demo

A working example can be found here: [robingenz/capacitor-plugin-demo](https://github.com/robingenz/capacitor-plugin-demo/tree/sponsorware)

| Android                    |
| -------------------------- |
| <img src="" width="324" /> |

## Roadmap

This plugin is still **under development**. We have already received feature requests. This is our approximate roadmap:

| Q4 2022                               |
| ------------------------------------- |
| - Extended Android Custom ROM support |

⚠️ **Disclaimer**: This roadmap does not represent a commitment, guarantee, obligation or promise to deliver any product or feature, or to deliver any product and feature by any particular date, and is intended to outline the general development plans. You should not rely on this roadmap to make any sponsorship decision.

## FAQ

1. **Which platforms are supported?**  
   This plugin supports Android (API Level 23+).
1. **Which Capacitor versions are supported?**  
   This plugin supports Capacitor 4.
1. **What do I do when I have a feature request?**  
   Please submit your feature request [here](https://github.com/capawesome-team/capacitor-android-battery-optimization/issues/new/choose). We will then review it and possibly put it on our roadmap.
1. **What do I do when I have found a bug?**  
   Bug reports have top priority. Please submit your bug report [here](https://github.com/capawesome-team/capacitor-android-battery-optimization/issues/new/choose). We will take a look at it as soon as possible.

## Installation

As long as the project is available as [Sponsorware](#sponsorware), the project will be distributed via GitHub packages.

1. Log in to GitHub package registry ([GitHub Docs](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#authenticating-to-github-packages)):

   ```
   $ npm login --scope=@capawesome-team --registry=https://npm.pkg.github.com

   > Username: USERNAME
   > Password: TOKEN
   > Email: PUBLIC-EMAIL-ADDRESS
   ```

1. In the same directory as your `package.json` file, create or edit an `.npmrc` file to include the following line ([GitHub Docs](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#installing-a-package)):
   ```
   @capawesome-team:registry=https://npm.pkg.github.com
   ```
1. Install the package:

   ```bash
   npm install @capawesome-team/capacitor-android-battery-optimization
   npx cap sync
   ```

   🆘 If you have any problems please [contact us by mail](mailto:support@capawesome.io) or [create a GitHub discussion](https://docs.github.com/en/discussions/quickstart#creating-a-new-discussion) in this repository.  
   ⚠️ **Attention**: Be careful not to disclose your npm auth token! If you have any questions (CI configuration etc.) please let us know.

### Android

This API requires the following permissions be added to your `AndroidManifest.xml` before the `application` tag:

```xml
<uses-permission android:name="android.permission.REQUEST_IGNORE_BATTERY_OPTIMIZATIONS" />
```

## Configuration

No configuration required for this plugin.

## Usage

```typescript
import { Capacitor } from '@capacitor/core';
import { BatteryOptimization } from '@capawesome-team/capacitor-android-battery-optimization';

const isBatteryOptimizationEnabled = async () => {
  if (Capacitor.getPlatform() !== 'android') {
    return false;
  }
  const { enabled } = await BatteryOptimization.isBatteryOptimizationEnabled();
  return enabled;
};

const openBatteryOptimizationSettings = async () => {
  if (Capacitor.getPlatform() !== 'android') {
    return;
  }
  await BatteryOptimization.openBatteryOptimizationSettings();
};

const requestIgnoreBatteryOptimization = async () => {
  if (Capacitor.getPlatform() !== 'android') {
    return;
  }
  await BatteryOptimization.requestIgnoreBatteryOptimization();
};
```

## API

<docgen-index>

* [`isBatteryOptimizationEnabled()`](#isbatteryoptimizationenabled)
* [`openBatteryOptimizationSettings()`](#openbatteryoptimizationsettings)
* [`requestIgnoreBatteryOptimization()`](#requestignorebatteryoptimization)
* [Interfaces](#interfaces)

</docgen-index>

<docgen-api>
<!--Update the source file JSDoc comments and rerun docgen to update the docs below-->

### isBatteryOptimizationEnabled()

```typescript
isBatteryOptimizationEnabled() => Promise<IsBatteryOptimizationEnabledResult>
```

Returns whether or not battery optimization is enabled.

Only available for Android.

**Returns:** <code>Promise&lt;<a href="#isbatteryoptimizationenabledresult">IsBatteryOptimizationEnabledResult</a>&gt;</code>

**Since:** 0.0.1

--------------------


### openBatteryOptimizationSettings()

```typescript
openBatteryOptimizationSettings() => Promise<void>
```

Opens the battery optimization settings page.

Only available for Android.

**Since:** 0.0.1

--------------------


### requestIgnoreBatteryOptimization()

```typescript
requestIgnoreBatteryOptimization() => Promise<void>
```

Requests the battery optimization ignore permission.

Only available for Android.

**Since:** 0.0.1

--------------------


### Interfaces


#### IsBatteryOptimizationEnabledResult

| Prop          | Type                 | Description                                     | Since |
| ------------- | -------------------- | ----------------------------------------------- | ----- |
| **`enabled`** | <code>boolean</code> | Whether or not battery optimization is enabled. | 0.0.1 |

</docgen-api>

## Changelog

See [CHANGELOG.md](https://github.com/capawesome-team/capacitor-android-battery-optimization/blob/main/CHANGELOG.md).

## License

See [LICENSE](https://github.com/capawesome-team/capacitor-android-battery-optimization/blob/main/LICENSE).
