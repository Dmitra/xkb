- convert key combination into another depending on active window
- bind cli command to key combination
+ do not interfere with Alt triggering window menu
+ convert key combination into another combination

# XKB
- Autokey cannot listen to new Alt (ShiftLevel5)
  - Create Super shortcuts
  - window-dependent shortcuts
- map Selection (Control+Alt+Shift+Arrows)
- emulate true Control+key sequences
  - Telegram C-z, C-x, C-c, C-v, C-a

# Tried
## Don't work
        interpret Alt_L+Exactly(52) {
            action = RedirectKey(keycode=<LEFT>, clearmodifiers=Mod1);
        };

## Works
        interpret z+AnyOfOrNone(all) {
            action = RedirectKey(keycode=<LEFT>, clearmodifiers=Mod1);
        };
        interpret AE+Exactly(None) {
            action = RedirectKey(keycode=<AB01>, clearmodifiers=Mod1, modifiers=Control);
        };

0 none
1 Shift
2 Lock
3 Shift+Lock
4 Control
5 Shift+Control
6 Lock+Control
7 Shift+Lock+Control
8 Mod1
9 Shift+Mod1
10 Lock+Mod1
11 Shift+Lock+Mod1
12 Control+Mod1
13 Shift+Control+Mod1
14 Lock+Control+Mod1
15 Shift+Lock+Control+Mod1
16 Mod2
511 all