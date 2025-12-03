# RD1-Pro Simple Toggle & Dim Blueprint (Zigbee2MQTT)

A minimal Home Assistant blueprint for the **Candeo RD1-Pro rotary dimmer** using **zigbee2mqtt**.

This blueprint supports:
- ✅ **Single press** → toggle light on/off  
- ✅ **Rotate right** → increase brightness  
- ✅ **Rotate left** → decrease brightness  

All advanced features from the original blueprint (multiple lights, double-press cycling, helpers, scenes) have been intentionally removed to keep setup and behavior simple and predictable.

---

## ✅ Requirements

- Home Assistant
- zigbee2mqtt integration
- One of the following Candeo devices:
  - `C-ZB-RD1P-REM`
  - `C-ZB-RD1P-DPM`
- A light entity that supports brightness control

---

## 🔧 Installation

1. Copy the blueprint YAML into a new file:
config/blueprints/automation/rd1p_simple_toggle_dim.yaml

2. Restart Home Assistant or reload automations.

3. Navigate to:
**Settings → Automations & Scenes → Blueprints**

4. Create a new automation using **“RD1-Pro simple toggle + dim (zigbee2mqtt)”**

---

## ⚙️ Blueprint Inputs

| Input | Description |
|-----|------------|
| **RD1-Pro Remote Device** | The physical Candeo rotary dimmer |
| **Light to control** | The single light entity to be controlled |
| **Brightness Step Percentage** | How much brightness increases per rotation step |
| **Negative Brightness Step** | How much brightness decreases per rotation step (must be negative) |

**Recommended defaults:**
- Brightness Up: `5%`
- Brightness Down: `-5%`

---

## 🚦 Controls Overview

| Action | Result |
|------|--------|
| Single Press | Toggle light on / off |
| Rotate Right | Increase brightness |
| Rotate Left | Decrease brightness |

> ℹ️ Brightness changes automatically turn the light **on** if it is off.

---

## ✂️ What’s intentionally excluded

This blueprint does **not** include:
- Light cycling / input_select helpers
- Double-press actions
- Scene control
- Long-press handling
- Multiple light targets

If you need any of those features, refer to the original Candeo blueprint.

---

## 🆚 Compared to Official Candeo Blueprint

| Feature | Official Blueprint | This Blueprint |
|------|------------------|---------------|
| Single light setup | ❌ | ✅ |
| Toggle on press | ✅ | ✅ |
| Rotary dimming | ✅ | ✅ |
| Multiple lights | ✅ | ❌ |
| Helpers required | ✅ | ❌ |
| Complexity | High | Very Low |

---

## 🛠 Customisation Ideas

- Duplicate the automation to control multiple rooms  
- Increase brightness step for faster response  
- Add long-press actions by extending the triggers  

If you want a **multi-light version without double-press cycling**, or a **long-press scene version**, just ask.

---

## 📄 License

This blueprint is provided as-is for personal use.  
Original inspiration from Candeo Smart Home – simplified for clarity and reliability.

