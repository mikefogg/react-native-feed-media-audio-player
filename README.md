
So...

The javascript bundler doesn't handle symbolic links in the node_modules
directory properly, so our plugin, 'react-native-feed-media-audio-player',
is in `example/node_modules/react-native-feed-media-audio-player/` and
the top level 'package' directory is a symbolic link to that dir.

To develop things, 

1. open the iOS app in XCode: `example/ios/example.xcodeproj`. Our native
  code is listed in `Libraries -> FNFMAudioPlayer.xcodeproj`.
2. start up the metro bundler package with `npm start`
  from the `example` dir.
3. open the javascript code in whatever editor you want: `package/*`

You build and start the app via XCode. That should build the native parts
and start them on the simulator. The simulator will ping the metro bundler
and load up the controlling javascript.

Once the app is running, hit command-D to show the debug menu. That lets
you control reloading. I suggest you turn on 'Live Reload' and also
click on 'Start Remote JS Debugging' so you can see console messages in 
a browser.


