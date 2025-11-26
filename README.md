# OWON OEL8511 Web Control Interface
# Work in progress. Do not use, unless for mevaluation of bug fix.
A modern, web-based control interface for the OWON OEL8511 Electronic Load using the Web Serial API. Control your electronic load directly from your browser with real-time monitoring, data logging, and battery testing capabilities.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Browser](https://img.shields.io/badge/browser-Chrome%20%7C%20Edge%20%7C%20Opera-orange)

<p align="center">
  <a href="https://www.paypal.com/paypalme/jobitjoseph">
    <img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" alt="Donate with PayPal" />
  </a>
</p>


![Main Image](https://github.com/jobitjoseph/owonconnect/blob/58137c9c6cb41ecd6bdcdb358903a67bae87b2e0/owonconnect.png)

## ✨ Features

### 🎮 **Multiple Operating Modes**
- **Constant Current (CC)** - Precision current sinking
- **Constant Voltage (CV)** - Voltage regulation mode
- **Constant Resistance (CR)** - Electronic resistance simulation
- **Constant Power (CP)** - Power dissipation control
- **Battery Test** - Automated discharge testing with capacity measurement

### 📊 **Real-Time Monitoring**
- Live voltage, current, and power readings
- Real-time graphing with Chart.js
- Configurable update rate (100-5000ms)
- Min/Max statistics tracking
- Capacity and energy measurements (mAh, Wh)
- Duration tracking with HH:MM:SS timer

### 🔧 **Advanced Controls**
- Adjustable current range (AUTO/LOW/HIGH)
- Slew rate control for smooth transitions
- Over-voltage protection (OVP)
- Over-current protection (OCP)
- Over-power protection (OPP)
- Short circuit protection
- Remote sensing capability
- Immediate device updates on value changes

### 🔋 **Battery Testing**
- Multiple battery chemistry presets (Li-ion, LiPo, LiFePO4, NiMH, NiCd, Lead Acid)
- Customizable discharge current
- Voltage cutoff with auto-stop
- Real-time State of Charge (SOC) calculation
- Discharge curve graphing
- Comprehensive test data logging

### 💾 **Data Export**
- CSV export of all measurements
- PNG snapshot of graphs
- Test reports with summary statistics

### 🎨 **Modern UI**
- Dark theme optimized for long sessions
- Material Design inspired interface
- Responsive layout
- Intuitive dial visualizations
- Color-coded readings
- Status indicators

## 🖥️ Browser Requirements

The Web Serial API is required to communicate with the device. Supported browsers:

| Browser | Minimum Version | Status |
|---------|----------------|--------|
| Google Chrome | 89+ | ✅ Fully Supported |
| Microsoft Edge | 89+ | ✅ Fully Supported |
| Opera | 75+ | ✅ Fully Supported |
| Brave | Latest | ✅ Fully Supported |
| Safari | Any | ❌ Not Supported |
| Firefox | Any | ❌ Not Supported |

## 🚀 Quick Start

### Installation

**No installation required!** This is a standalone HTML file.

1. Download `owon_web_complete.html`
2. Double-click to open in your browser, or
3. Host on a web server for HTTPS access

### First Time Setup

1. **Open the file** in Chrome, Edge, or Opera
2. **Connect your OWON OEL8511** via USB
3. **Click "🔌 Connect"** button
4. **Select your device** from the port list (usually "USB-SERIAL CH340" or similar)
5. **Device connects automatically** and reads current settings

### Serial Settings

The application automatically configures:
- **Baud Rate**: 115200
- **Data Bits**: 8
- **Stop Bits**: 1
- **Parity**: None
- **Flow Control**: None

## 📖 Usage Guide

### Basic Operation

#### 1. **Select Mode**
```
Sidebar → Click CC/CV/CR/CP/Dynamic button
Device automatically switches mode
Settings populate from device
```

#### 2. **Set Parameters**
```
Enter value in input field
Press Enter or Tab
Command immediately sent to device
Dial updates to show setting
```

#### 3. **Enable Load**
```
Click "🟢 INPUT ON" button
Load activates
Real-time monitoring begins
Graph starts recording
```

#### 4. **Monitor & Log**
```
Watch live readings update
View real-time graph
Statistics tracked automatically
Export data when complete
```

### Constant Current (CC) Mode

**Use Case**: Discharge testing, LED testing, current source simulation

1. Select **Load > CC** from sidebar
2. **Set Current**: Enter desired current (0-20A)
3. **Configure Settings**:
   - Current Range: AUTO/LOW/HIGH
   - Slew Rate: Transition speed (A/μs)
   - Current Limit: Maximum current
   - Voltage On Level: Turn-on threshold
4. **Enable Protections**:
   - OVP: Over-voltage protection
   - OCP: Over-current protection
   - OPP: Over-power protection
5. Click **INPUT ON**
6. Monitor load in real-time

### Constant Voltage (CV) Mode

**Use Case**: Battery charging simulation, voltage regulation testing

1. Select **Load > CV** from sidebar
2. **Set Voltage**: Enter desired voltage (0-150V)
3. **Configure Settings**:
   - Voltage Range: AUTO/LOW/HIGH
   - Current Limit: Maximum current draw
   - Remote Sensing: Enable for accurate voltage
4. Click **INPUT ON**

### Constant Resistance (CR) Mode

**Use Case**: Resistive load simulation, heater testing

1. Select **Load > CR** from sidebar
2. **Set Resistance**: Enter desired resistance (Ω)
3. **Configure Settings**:
   - Current Limit: Safety limit
   - Power Limit: Maximum power
4. Click **INPUT ON**

### Constant Power (CP) Mode

**Use Case**: Power supply testing, thermal testing

1. Select **Load > CP** from sidebar
2. **Set Power**: Enter desired power (0-200W)
3. **Configure Settings**:
   - Voltage Limit: Maximum voltage
   - Current Limit: Maximum current
   - Slew Rate: Power transition speed
4. Click **INPUT ON**

### Battery Testing

**Complete discharge capacity test with automatic cutoff**

#### Setup

1. Click **🔋 Battery** in sidebar
2. **Configure Battery**:
   - Battery Type: Select chemistry (Li-ion, LiPo, etc.)
   - Cell Count: Number of cells in series
   - Rated Capacity: Expected capacity (mAh)
3. **Set Test Parameters**:
   - Discharge Current: Test current (A)
   - Cut-off Voltage: End voltage (V)
   - Auto Stop: Enable automatic termination
4. **Connect Battery** to load terminals

#### Running Test

1. Click **▶️ Start Test**
   - Device switches to CC mode
   - Discharge current applied
   - Monitoring begins
2. **Watch Progress**:
   - SOC percentage with progress bar
   - Discharged capacity (mAh)
   - Energy delivered (Wh)
   - Average voltage
   - Test duration
3. **Test Completes**:
   - Auto-stops at cutoff voltage
   - Final statistics displayed
   - Data ready for export

#### Test Results

```
Battery Test Completed!

Cutoff voltage reached: 3.00V
Capacity: 2450 mAh
Energy: 9.05 Wh
Duration: 01:13:25
```

### Data Export

#### CSV Export

Click **💾 Save Data** to export:
```csv
Time,Voltage,Current,Power,Capacity
0.0,12.345,2.000,24.690,0
0.5,12.340,2.000,24.680,0.3
1.0,12.335,2.000,24.670,0.5
...
```

#### Graph Snapshot

Click **📸 Snapshot** to save:
- PNG image of current graph
- Filename includes mode and timestamp
- Example: `owon_CC_graph_2025-11-26T14-30-00.png`

## 🔌 SCPI Command Reference

### Query Commands

| Command | Description | Response |
|---------|-------------|----------|
| `FUNC?` | Read current mode | CURR/VOLT/RES/POW |
| `CURR?` | Read current setpoint | Value in Amps |
| `VOLT?` | Read voltage setpoint | Value in Volts |
| `RES?` | Read resistance setpoint | Value in Ohms |
| `POW?` | Read power setpoint | Value in Watts |
| `MEAS:VOLT?` | Measure voltage | Measured voltage |
| `MEAS:CURR?` | Measure current | Measured current |
| `MEAS:POW?` | Measure power | Measured power |
| `INP?` | Read input state | ON/OFF or 1/0 |
| `CURR:RANG?` | Read current range | AUTO/LOW/HIGH |
| `VOLT:PROT?` | Read OVP value | Value in Volts |
| `CURR:PROT?` | Read OCP value | Value in Amps |
| `POW:PROT?` | Read OPP value | Value in Watts |

### Control Commands

| Command | Description | Example |
|---------|-------------|---------|
| `FUNC CURR` | Set CC mode | `FUNC CURR` |
| `FUNC VOLT` | Set CV mode | `FUNC VOLT` |
| `FUNC RES` | Set CR mode | `FUNC RES` |
| `FUNC POW` | Set CP mode | `FUNC POW` |
| `CURR <value>` | Set current | `CURR 2.500` |
| `VOLT <value>` | Set voltage | `VOLT 12.000` |
| `RES <value>` | Set resistance | `RES 10.000` |
| `POW <value>` | Set power | `POW 50.00` |
| `INP ON` | Enable input | `INP ON` |
| `INP OFF` | Disable input | `INP OFF` |
| `CURR:RANG AUTO` | Set current range | AUTO/LOW/HIGH |
| `CURR:SLEW <value>` | Set slew rate | `CURR:SLEW 0.100` |
| `VOLT:PROT <value>` | Set OVP value | `VOLT:PROT 150` |
| `VOLT:PROT:STAT ON` | Enable OVP | ON/OFF |
| `CURR:PROT <value>` | Set OCP value | `CURR:PROT 20` |
| `POW:PROT <value>` | Set OPP value | `POW:PROT 200` |
| `CURR:SHOR ON` | Enable short circuit | ON/OFF |
| `SENS:REM ON` | Enable remote sensing | ON/OFF |
| `SYST:REM` | Enter remote mode | - |
| `SYST:LOC` | Return to local mode | - |

## ⚙️ Configuration

### Update Rate

Control how often measurements are taken:

```
Settings Panel → Update Rate
Range: 100-5000ms
Default: 500ms (2 samples/second)
```

**Recommendations**:
- **100-250ms**: Fast transients, dynamic testing
- **500ms**: Normal operation (default)
- **1000-2000ms**: Long duration tests, reduced data
- **5000ms**: Multi-hour tests, minimal logging

### Buffer Size

Control how many data points to keep in memory:

```
Settings Panel → Buffer Size
Range: 100-10000 points
Default: 1000 points
```

**Recommendations**:
- **100-500**: Short tests, quick response
- **1000**: Normal operation (default)
- **5000-10000**: Long tests with high update rate

### Graph Controls

Customize what's displayed:

- ☑️ **Voltage** - Blue trace
- ☑️ **Current** - Green trace
- ☑️ **Power** - Red trace
- ☐ **Capacity** - Purple trace (optional)

## 🔧 Troubleshooting

### Device Not Found

**Problem**: No serial port appears in connection dialog

**Solutions**:
1. Check USB cable connection
2. Install CH340 driver if needed (Windows)
3. Try different USB port
4. Restart browser
5. Check device power

### Connection Failed

**Problem**: Error when clicking Connect button

**Solutions**:
1. Close other applications using the port
2. Disconnect and reconnect device
3. Refresh browser page
4. Check serial settings match device

### Invalid Readings

**Problem**: Voltage/current showing zeros or wrong values

**Solutions**:
1. Check console for validation warnings
2. Ensure INPUT is enabled on device
3. Verify SCPI commands supported
4. Check device firmware version
5. Try lower update rate

### Settings Not Reading

**Problem**: Configuration fields remain empty

**Solutions**:
1. Wait 5 seconds for periodic update
2. Check console for "not supported" messages
3. Ensure device in correct mode
4. Try manual entry
5. Device may not support query command

### Short Circuit Not Working

**Problem**: Cannot enable/disable short circuit

**Solutions**:
1. Check console for error messages
2. Command may not be supported by device
3. Try via device front panel
4. Check firmware version
5. Feature may require specific hardware

### Web Serial API Not Available

**Problem**: Browser doesn't support Web Serial API

**Solutions**:
1. Use Chrome 89+, Edge 89+, or Opera 75+
2. Enable chrome://flags/#enable-experimental-web-platform-features
3. Use HTTPS connection (not http://)
4. Try different browser

### Data Export Issues

**Problem**: CSV or PNG not downloading

**Solutions**:
1. Check browser download permissions
2. Clear browser cache
3. Try different download location
4. Check disk space
5. Disable popup blocker

## 🛡️ Safety & Best Practices

### Safety Guidelines

⚠️ **Always follow proper safety procedures:**

1. **Power Limits**: Never exceed device ratings (150V, 20A, 200W)
2. **Heat Management**: Ensure adequate cooling during high-power operation
3. **Battery Testing**: Monitor temperature, never leave unattended
4. **Polarity**: Verify correct polarity before connection
5. **Fusing**: Use appropriate fuses in your circuit
6. **Isolation**: Ensure proper electrical isolation

### Best Practices

✅ **For Reliable Testing:**

1. **Warm Up**: Allow 10 minutes warm-up before precision testing
2. **Calibration**: Regularly verify readings with known references
3. **Cable Quality**: Use short, heavy gauge cables to minimize resistance
4. **Ventilation**: Maintain good airflow around device
5. **Data Backup**: Export data regularly during long tests
6. **Range Selection**: Use appropriate current range for accuracy
7. **Remote Sensing**: Enable for accurate voltage measurements
8. **Update Rate**: Balance between resolution and data volume

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 Jobit Joseph

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 👤 Author

**Jobit Joseph**

- GitHub: [@jobitjoseph](https://github.com/jobitjoseph)
- YouTube: [Electronics Channel](https://youtube.com/@jobitjoseph)
- PayPal: [Support Development](https://paypal.me/jobitjoseph)

## 🙏 Acknowledgments

- **OWON** - For the OEL8511 Electronic Load
- **Chart.js** - For the excellent graphing library
- **Web Serial API** - For enabling browser-to-device communication
- **Community** - For feedback, testing, and suggestions

## 📊 Project Status

- **Version**: 1.0.0
- **Status**: Active Development
- **Last Updated**: November 2025
- **Stability**: Stable

## 🌟 Star History

If you find this project useful, please consider giving it a ⭐ on GitHub!

---

**Made with ❤️ for the electronics community**
