# macos-push-to-talk

A very simple "push to talk" functionality for microphone on macOS. An inverted audio "killswitch".

Requires Python 3, osascript and pynput

```shell
% pip3 install pynput
% pip3 install osascript
```

Run and keep the console open in background. 

```shell
% python3 ./push-to-talk.py
Your mic is now muted. Press and hold 'alt_r' to talk...
```

Press right "option" key to talk, release to mute.

## Why the fork?

Catalina has a more granular permissions framework. `root` permissions are not requried for input monitoring, so we can simplify the script a little by taking the `sudo` step out.

## Why is it asking to monitor my keyboard input?

In order to monitor keyboard events to make push-to-talk work whilst other applications have focus, permissions will be requested. When the dialog opens, click to get through to System Preferences and click the padlock; enter your password and tick "Terminal" or "iTerm" (or whichever terminal you used to launch the script above). You'll need to restart the terminal and relaunch `push-to-talk.py` before the permission can take effect. If you reject this permission, the hotkey will only operate when you have the launch terminal open.

## Disclaimer

(by the author, @brunorey)

> Tested only on my mac (macbook pro early 2019, mojave 10.14.6), so no guarantees that it'll work on any other device. At the moment, it's built only for my needs. Hopefully that'll improve over time.
