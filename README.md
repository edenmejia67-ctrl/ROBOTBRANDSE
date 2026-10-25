# ARPCS Circuit Simulator

Interactive 3D and 2D circuit view for the **Automatic Roadside Plant-Control System (ARPCS)**.
The HC-SR04 measures plant height. At 60 cm or taller (DPWH limit), the Arduino closes a relay,
the pump sprays herbicide or growth regulator, and the servo sweeps the nozzle from 0° to 180°.

Single file, no build step: open `index.html` in a browser.
Internet is needed for Three.js (cdnjs) and Google Fonts.

## Parts
Arduino Uno + USB, HC-SR04, 180° servo, 3.7 V submersible pump, 1 m tube, spray nozzle,
3.7 V 2500 mAh battery, switch, 1-channel relay module, breadboard, M-M and M-F jumpers.

## Wiring
| From | To |
|------|----|
| Arduino 5V | HC-SR04 VCC, relay VCC |
| Arduino GND | GND rail (shared by every part) |
| D7 / D6 | HC-SR04 TRIG / ECHO |
| D8 | Relay IN (active LOW) |
| D9 | Servo signal |
| Battery + | Switch, then relay COM and breadboard + rail |
| Relay NO | Pump + |
| Pump -, Battery -, Servo GND | GND rail |
| Servo V | Battery + rail (after the switch) |

Arduino is powered by USB. The battery powers the servo and pump only.
Tip: add a 1N4007 diode across the pump. A 3.7 V line may be weak for some servos, so test first.

## Controls
- 3D / 2D toggle, Overview button
- Battery switch, plant height slider (10 to 120 cm), hide jumper wires
- Click a part (or the legend) to focus and read what it does

## Publish on GitHub Pages
1. Create a repository and upload all files in this folder.
2. Settings, Pages, Source: Deploy from a branch, `main`, `/ (root)`.
3. Open `https://<username>.github.io/<repo>/`.

## Files
- `index.html` the simulator
- `docs/HANDOFF.md` planning notes
- `.nojekyll`, `LICENSE` (MIT)
