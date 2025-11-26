# Quick Start Guide - OWON OEL8511 Web Control

Get up and running in 5 minutes!

## What You Need

✅ OWON OEL8511 Electronic Load  
✅ USB Cable  
✅ Chrome, Edge, or Opera browser (89+)  
✅ `owon_web_complete.html` file

## Step-by-Step Setup

### 1️⃣ Connect Hardware

```
OWON OEL8511 → USB Cable → Computer
```

Make sure the device is powered on.

### 2️⃣ Open Application

**Option A: Local File**
- Double-click `owon_web_complete.html`
- Opens in your default browser

**Option B: Web Server**
- Host file on local/remote server
- Navigate to URL in browser

### 3️⃣ Connect to Device

1. Click **🔌 Connect** button (top right)
2. Browser shows port selection dialog
3. Select your device (usually "USB-SERIAL CH340")
4. Click **Connect**

✅ **Connected!** Status shows green dot and "Connected"

### 4️⃣ Select Mode

**In Left Sidebar:**
- Click **Load** button (should be active)
- Choose mode: **CC** / **CV** / **CR** / **CP**

Device automatically switches mode and reads settings.

### 5️⃣ Set Parameters

**Example: Constant Current (CC) Mode**

1. **Set Current**: Type `2.500` in main input box → Press Enter
   - Dial rotates to show 2.5A
   - Command sent to device immediately

2. **Configure Settings** (optional):
   - Current Range: AUTO (recommended)
   - OVP: ✅ 150V
   - OCP: ✅ 20A
   - OPP: ✅ 200W

### 6️⃣ Enable Load

Click **🟢 INPUT ON** button

- Button changes to **🔴 INPUT OFF**
- Load activates
- Monitoring begins
- Graph starts plotting

### 7️⃣ Monitor

**Live Readings Panel (Right Side):**
- **Voltage**: Current voltage
- **Current**: Current draw
- **Power**: Power dissipation
- **Capacity**: mAh counter
- **Energy**: Wh counter

**Graph:**
- Blue = Voltage
- Green = Current
- Red = Power
- Purple = Capacity (if enabled)

### 8️⃣ Stop & Export

1. Click **🔴 INPUT OFF** to disable load
2. Click **💾 Save Data** to export CSV
3. Click **📸 Snapshot** to save graph as PNG

## Common Modes

### 🔌 Constant Current (CC)

**Use For:** Battery discharge testing, LED testing

```
1. Load > CC
2. Set Current: 2.000 A
3. Set OVP: 150 V
4. INPUT ON
```

### 🔋 Battery Test

**Use For:** Capacity testing with auto-cutoff

```
1. Click 🔋 Battery
2. Battery Type: Li-ion
3. Discharge Current: 2.000 A
4. Cutoff Voltage: 3.0 V
5. Click ▶️ Start Test
```

Test automatically stops at cutoff voltage.

### ⚡ Constant Voltage (CV)

**Use For:** Charger simulation

```
1. Load > CV
2. Set Voltage: 12.000 V
3. Current Limit: 5.000 A
4. INPUT ON
```

### 🔥 Constant Power (CP)

**Use For:** Power supply testing

```
1. Load > CP
2. Set Power: 50.00 W
3. Voltage Limit: 150 V
4. INPUT ON
```

## Tips for Success

### ✅ DO:
- Wait for green "Connected" indicator
- Use AUTO current range for most tests
- Enable OVP/OCP/OPP protections
- Export data regularly during long tests
- Check console (F12) if issues occur

### ❌ DON'T:
- Don't exceed device ratings (150V, 20A, 200W)
- Don't leave battery tests unattended
- Don't use Safari or Firefox (not supported)
- Don't disconnect USB while input is ON
- Don't ignore temperature warnings

## Troubleshooting

### No Device Found?
```
1. Check USB cable
2. Install CH340 driver (Windows)
3. Try different USB port
4. Restart browser
```

### Can't Connect?
```
1. Close other serial programs
2. Refresh browser page
3. Disconnect & reconnect device
```

### Wrong Readings?
```
1. Check console (F12) for errors
2. Ensure INPUT is ON
3. Try lower update rate
4. Verify device mode
```

### Settings Not Loading?
```
1. Wait 5-10 seconds
2. Check console for "not supported"
3. Some features vary by firmware
```

## keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Enter` | Apply current setting value |
| `Tab` | Move to next input field |
| `F12` | Open browser console |
| `Ctrl + R` | Reload page |

## Data Files

### CSV Export Format
```csv
Time,Voltage,Current,Power,Capacity
0.0,12.345,2.000,24.690,0.0
0.5,12.340,2.000,24.680,0.3
1.0,12.335,2.000,24.670,0.5
```

**Opens in:** Excel, Google Sheets, LibreOffice

### PNG Snapshot
- Full-resolution graph image
- Timestamped filename
- All visible traces included

## Need More Help?

📖 **Full Documentation**: See README.md  
🐛 **Issues**: [GitHub Issues](https://github.com/jobitjoseph/owonconnect/issues)  
💬 **Discussions**: [GitHub Discussions](https://github.com/jobitjoseph/owonconnect/discussions)  

## Quick Reference

### SCPI Commands
```
FUNC CURR          → Set CC mode
CURR 2.500         → Set 2.5A
INP ON             → Enable input
INP OFF            → Disable input
MEAS:VOLT?         → Read voltage
MEAS:CURR?         → Read current
```

### Device Ratings
```
Voltage: 0-150V
Current: 0-20A
Power: 0-200W
Accuracy: 0.05%
```

### Update Rate
```
Fast: 100-250ms    → Dynamic tests
Normal: 500ms      → General use
Slow: 1000-5000ms  → Long tests
```

---

**Happy Testing! 🎉**

For detailed information, see [README.md](README.md)
