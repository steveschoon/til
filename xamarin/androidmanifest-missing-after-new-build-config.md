# AndroidManifest missing in CSPROJ When Create New Build Config

After creating a new build config in a Xamarin solution that has an Android project, have to take these steps to make the new build config point to an AndroidManifest.xml file:

- Unload the Android CSPROJ from the solution
- Edit the Android CSPROJ file with a text editor
- Add `<AndroidManifest>Properties\AndroidManifest.xml</AndroidManifest>` in the section for the build config just created

This was causing confusion in Bitrise builds because IF the CSPROJ file section for a build configuragion doesn't point to an AndroidManifest.xml,  the minimum required android version will default to the target Android version, which is usually higher than what you want.
