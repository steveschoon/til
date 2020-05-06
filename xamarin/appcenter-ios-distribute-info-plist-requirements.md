# AppCenter iOS Distribute Info.plist Requirements

Distributing updates to an iOS app through AppCenter won't detect new versions and offer to update unless the following is in Info.plist

```
<key>CFBundleURLTypes</key>
<array>
  <dict>
  	<key>CFBundleURLSchemes</key>
  	<array>
  		<string>appcenter-{APP_SECRET}</string>
  	</array>
  </dict>
</array>
```

More details here: https://docs.microsoft.com/en-us/appcenter/sdk/distribute/ios
