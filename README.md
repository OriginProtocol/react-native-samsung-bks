# react-native-samsung-bks

![npm_version](https://img.shields.io/npm/v/react-native-samsung-bks.svg?style=flat-square&colorA=111d28&colorB=1a82ff)
[![license](https://img.shields.io/badge/license-MIT-6e3bea.svg?style=flat-square&colorA=111d28)](https://github.com/OriginProtocol/react-native-samsung-bks/blob/master/LICENSE)

React Native wrapper for the Samsung Blockchain Keystore SDK

## Getting started

`$ npm install react-native-samsung-bks --save`

### Automatic installatation (RN > 0.60)

### Mostly automatic installation (RN < 0.59.x)

`$ react-native link react-native-samsung-bks`

Add the following into the root project `build.gradle`

```
allprojects {
    ...
    repositories {
        ...
        flatDir {
            dirs "$rootDir/aar"
        }
    }
}
```

Download the Samsung Blockchain Keystore SDK aar file and put it in `android/aar`.

### Manual installation

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.reactlibrary.RNSamsungBKS;` to the imports at the top of the file
  - Add `new RNSamsungBKS()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-samsung-bks'
  	project(':react-native-samsung-bks').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-react-native-sbksdk/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      implementation project(':react-native-samsung-bks')
  	```
4. Add the following into the root project `build.gradle`

```
allprojects {
    ...
    repositories {
        ...
        flatDir {
            dirs "$rootDir/aar"
        }
    }
}
```


## Usage
```javascript
import RNSamsungBKS from 'react-native-samsung-bks';

```

The following methods of the SDK are available:

`RNSamsungBKS.isSupported()`

`RNSamsungBKS.getDeepLinks()`

`RNSamsungBKS.getSeedHash()`

`RNSamsungBKS.checkForMandatoryAppUpdate()`

`RNSamsungBKS.getAddressList(hdPath)`

`RNSamsungBKS.signEthTransaction(hdPath, nonce, gasPrice, gasLimit, to, value, data)`

`RNSamsungBKS.signEthPersonalMessage(hdPath, b64MessageToSign)`
