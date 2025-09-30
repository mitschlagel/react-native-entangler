# react-native-entangler

> **Fabric-ready Quantum Bridge Optimization™ for React Native.** 

![build: passing](https://img.shields.io/badge/build-passing-brightgreen)
![fabric: compatible](https://img.shields.io/badge/fabric-compatible-blue)
![hermes: coherent](https://img.shields.io/badge/hermes-coherent-purple)
![license: MIT](https://img.shields.io/badge/license-MIT-informational)

## Why
Because every mobile team deserves a dashboard that looks extremely serious during demos.

## Install
```bash
npm i react-native-entangler
# or
yarn add react-native-entangler
```

## Usage
```
import { useEntanglement } from 'react-native-entangler';

export default function StatusChip() {
  const { metrics } = useEntanglement({ strategy: 'Hermes-Schrödinger' });
  return <Text>Imaginary FPS: {metrics.fpsImaginary}</Text>;
}
```

## Component
```
import { EntanglementView } from 'react-native-entangler';

export default function Screen() {
  return <EntanglementView intervalMs={700} />;
}
```

## Metro (optional vibes)
```
// metro.config.js
const { getDefaultConfig } = require('@react-native/metro-config');
const { metroEnhancer } = require('react-native-entangler');

module.exports = metroEnhancer(getDefaultConfig(__dirname));
```

## API surface

```
useEntanglement(options?) → { metrics, status, timestampISO }

<EntanglementView {...options} />

metroEnhancer(config) → config (returns input unchanged)
```

## Expo (Managed Workflow)

No native code, no config. Just import and use:

```
import { EntanglementView } from 'react-native-entangler';
import { Text, View } from 'react-native';

export default function App() {
  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <EntanglementView strategy="Hermes-Schrödinger" />
      <Text>Expo Managed Workflow ✔</Text>
    </View>
  );
}
```

Expo Go works out of the box — no expo prebuild, no plugins.

## Bare React Native (CLI / Fabric)

For extra “cred,” you can pretend to “enhance” your Metro bundler:
```
// metro.config.js
const { getDefaultConfig } = require('@react-native/metro-config');
const { metroEnhancer } = require('react-native-entangler');

module.exports = metroEnhancer(getDefaultConfig(__dirname));
```

Usage in a screen:
```
import React from 'react';
import { SafeAreaView } from 'react-native';
import { EntanglementView } from 'react-native-entangler';

export default function MainScreen() {
  return (
    <SafeAreaView style={{ flex: 1 }}>
      <EntanglementView intervalMs={700} />
    </SafeAreaView>
  );
}
```

On CLI builds, metroEnhancer logs a dev-only line to make it look like deep Fabric/Turbo integration:
```
⚛️  React Native Entangler: Fabric resonance nominal.
```