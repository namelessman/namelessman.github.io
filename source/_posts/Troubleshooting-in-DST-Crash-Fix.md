title: Troubleshooting in DST Crash Fix
date: 2025-03-11 19:54:41
tags:

---

# Troubleshooting in DST Crash Fix

I played the game named "Don't Starve together" with friends at night. It's one of my favorite games and I got a friend to play together!

We were in the caves, then an earthquake happened that didn't stop until the worm hole appeared and the worm was supposed to show. Unfortunately, we crashed.

<!-- more -->

We spent one hour to try to rollback and restart the server; however, the issue still couldn't be fixed.

{% asset_img "crash.png" "Crash" %}

## Logs

Since the game means a lot to me and we've spent weeks on this save, I can't bear to lose our progress.

I searched on the internet, and got a [log reader](https://logreader.netlify.app/en/) tool instead. But as a player, there were a lot of logs in the folders. So I uploaded the log files to ChatGPT to help analyze the crash logs. Then I found an error:

```
[string "../mods/workshop-2078243581/modmain.lua"]:69: attempt to index field 'sg' (a nil value)
```

and got the corresponding log file.

Open the log file by the log reader, and can find the error where it came from.

The mod is trying to show the attack range of the worm, however, the worm was added into the game recently. So the mod reads a nil value and the game crashes.

{% asset_img "log.png" "Log" %}

## Fix

Disable the mod.

## Conclusion

It's really annoying to debug at midnight, especially it's a game, not supposed to work.
