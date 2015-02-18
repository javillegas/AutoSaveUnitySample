# AutoSaveUnitySample
Shows how to have a simple auto save functionality in Unity with Google Play Game Services

For complete documentation see: https://github.com/playgameservices/play-games-plugin-for-unity

PLEASE post questions there vs. my repository - oddly, not many people look at this repo :).

There are a lot of steps and callbacks in order to save data using the Saved Games API and Unity, so I made a 
simple example that is super simple to demonstrate saving and loading a couple fields.

I serialized the values to a delmited string for simplicitity. A more robust serialization could be used for a lot of data.

When the game starts, it logs in the user (make sure they are a tester on the play console).  Once the login
is successful, the auto saved game data is loaded.

Change the values, and then click save.  This saves the data (ok - not exactly autosaved, but you get the idea).

Exit the game, or start on another device - the game data will be there.

Setup the game on the Play console before running this application, the saved game system caches information on the 
device, and if you run the game before enabling saved games, you either need to wait 24 hours, or clear the Play Services Data on the device.  This is a pain - and Google is working on improving that.

To Configure the game:

1. Go to games console (https://play.google.com/apps/publish/)
     - see https://developers.google.com/games/services/console/enabling
2. Add new game
3. Turn on Saved Games, click Save
4. Click Linked apps.
      then android
5. Set the package name (and remember it)
6. Save and continue
7. Click "Authorize your app now"
8. click continue.
9. get the fingerprint of your debug key:
   - keytool -list -v -keystore "%USERPROFILE%\.android\debug.keystore" -alias androiddebugkey -storepass android -keypass android
10. paste in the SHA1 fingerprint and continue.  
11. copy the client id.  
       - NOTE: for android you only need the number part.

Go to Unity.
1. Import the Google Play Game Services plugin.
2.  Click Google Play Games/Android Setup.
3. enter the client id for the application id.
4. if you get a warning about version  6111000 and you know you have a new version of the SDK, click OK.
5 . File/Build Settings....
       - change the type to Android
6. click player settings
      -  other settings - bundle id - paste in the package name you configured.
      - publishing settings - select the debug keystore and the androiddebugkey alias
8. Import autosavesample.unitypackage (from this repo).
7. Click build and run.




