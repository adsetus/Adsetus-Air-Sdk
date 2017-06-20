# Adsetus AIR SDK
SDK Version: 1.0.6

## Overview
...

## Quick Start
### 1. Add ANE file to your project

##### A. Flash Professional (or Adobe Animate):
```
  1.    Open ActionScript Settings (File -> ActionScript Settings)
  2.    Select the Library Path tab.
  3.    Select the "Browse to a Native Extenion (ANE) file" button"
  4.    Browse to the ANE file and select it.
```
##### B. Flash Builder:
```
  1.    Open Project Properties (File -> Properties)
  2.    Select Flex Build Path from the side bar.
  3.    Select the Native Extensions tab.
  4.    Select the Add ANE button.
  5.    Browse to the ANE file and select it.
```

### 2. Edit Your Application's Descriptor
Add the following text to your application's XML descriptor:
```
<extensions>
    <extensionID>us.adset.sdk.plugin.air</extensionID>
</extensions>
```

Include the following XML after the \</extensions> tag in your application's XML descriptor:
```
<android>
    <manifestAdditions>
        <![CDATA[
        <manifest android:installLocation="auto">
            <!-- Required Permissions -->
            <uses-permission android:name="android.permission.INTERNET"/>
            <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
            <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>

            <!-- Optional Permissions -->
            <uses-permission android:name="android.permission.GET_ACCOUNTS" />
            <uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
            <uses-permission android:name="android.permission.READ_PHONE_STATE" />
            <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
            <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />

            <application>
                <!-- Required Activities -->

                <activity android:name="com.unity3d.ads.adunit.AdUnitActivity"
                    android:configChanges="fontScale|keyboard|keyboardHidden|locale|mnc|mcc|navigation|orientation|screenLayout|screenSize|smallestScreenSize|uiMode|touchscreen"
                    android:hardwareAccelerated="true"
                    android:theme="@android:style/Theme.NoTitleBar.Fullscreen" />

                <activity android:name="com.unity3d.ads.adunit.AdUnitSoftwareActivity"
                    android:configChanges="fontScale|keyboard|keyboardHidden|locale|mnc|mcc|navigation|orientation|screenLayout|screenSize|smallestScreenSize|uiMode|touchscreen"
                    android:hardwareAccelerated="false"
                    android:theme="@android:style/Theme.NoTitleBar.Fullscreen" />

                <activity android:name="com.vungle.publisher.VideoFullScreenAdActivity"
                    android:configChanges="keyboardHidden|orientation|screenSize|screenLayout|smallestScreenSize"
                    android:theme="@android:style/Theme.NoTitleBar.Fullscreen" />

                <activity android:name="com.vungle.publisher.MraidFullScreenAdActivity"
                    android:configChanges="keyboardHidden|orientation|screenSize|screenLayout|smallestScreenSize"
                    android:theme="@android:style/Theme.Translucent.NoTitleBar.Fullscreen" />

                <activity android:name="com.chartboost.sdk.CBImpressionActivity"
                    android:configChanges="keyboardHidden|orientation|screenSize"
                    android:excludeFromRecents="true"
                    android:hardwareAccelerated="true"
                    android:theme="@android:style/Theme.Translucent.NoTitleBar.Fullscreen" />

                <activity android:name="com.adcolony.sdk.AdColonyInterstitialActivity"
                    android:configChanges="keyboardHidden|orientation|screenSize"
                    android:hardwareAccelerated="true" />

                <activity android:name="com.adcolony.sdk.AdColonyAdViewActivity"
                    android:configChanges="keyboardHidden|orientation|screenSize"
                    android:hardwareAccelerated="true" />

                <activity android:name="com.startapp.android.publish.list3d.List3DActivity"
                    android:theme="@android:style/Theme" />

                <activity android:name="com.startapp.android.publish.OverlayActivity"
                    android:theme="@android:style/Theme.Translucent"
                    android:configChanges="orientation|keyboardHidden|screenSize" />

                <activity android:name="com.startapp.android.publish.FullScreenActivity"
                    android:theme="@android:style/Theme"
                    android:configChanges="orientation|keyboardHidden|screenSize" />

                <activity android:name="com.applovin.adview.AppLovinInterstitialActivity" />

                <activity android:name="com.applovin.adview.AppLovinConfirmationActivity" />
            </application>
        </manifest>
        ]]>
    </manifestAdditions>

</android>
```

### 4. Initialize SDK

```Java
Adsetus.init("YOUR_APP_ID");	
```

### 5. Play an Ad

```Java
Adsetus.showAd();
```