Here are the ADB commands to test every action locally — no Google Assistant needed.

**Replace `<PACKAGE>` with `com.poc.quickcontrols`** and `<ACTIVITY>` with the actual VoiceActionActivity path (likely `com.poc.quickcontrols.voice.VoiceActionActivity`).

---

### 🔦 Torch
```bash
# Turn ON
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature torch_on

# Turn OFF
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature torch_off
```

### 🔇 Do Not Disturb
```bash
# Enable
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature dnd_on

# Disable
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature dnd_off
```

### 🔊 Volume
```bash
# Mute
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature volume_mute

# Unmute
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature volume_unmute

# Volume up
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature volume_up

# Volume down
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature volume_down

# Max volume
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature volume_max
```

### 🌙 Dark Mode
```bash
# Dark mode ON
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature dark_mode_on

# Light mode
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature dark_mode_off
```

### 📳 Ringer Mode
```bash
# Silent
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature ringer_silent

# Vibrate
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature ringer_vibrate

# Normal
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature ringer_normal
```

### 🟢 Local VPN
```bash
# Connect
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature vpn_connect

# Disconnect
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature vpn_disconnect
```

### 💼 Work Mode (composite)
```bash
# Start Work Mode (DND + mute + VPN + dark mode)
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature work_mode_on

# End Work Mode
adb shell am start -n com.poc.quickcontrols/.voice.VoiceActionActivity -a android.intent.action.VIEW --es feature work_mode_off
```

---

### 🔧 Helpful debug commands

```bash
# Verify shortcuts are registered
adb shell cmd shortcut get-shortcuts com.poc.quickcontrols

# See app logs while testing
adb logcat | grep -i "quickcontrols\|voiceaction\|actionhandler"

# Check if the activity exists
adb shell pm dump com.poc.quickcontrols | grep VoiceActionActivity
```

---

### ✅ Expected output

For each command, you should see:
```
Starting: Intent { ... }
```

If you see `Error type 3` → activity name is wrong, double-check the path in your manifest.

Save these in a `test-commands.sh` file in the project root for easy testing. 🚀



Maximize compose field
Attach an image to your conversation with Anu Preetha L G
Attach a file to your conversation with Anu Preetha L G
Open
