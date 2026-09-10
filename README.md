# IR Remote for M515_V1.1 Bluetooth Speaker

## Board

- Board: `M515_V1.1` (generic Chinese BT/FM/AUX/USB decoder board)
- IR receiver: 38kHz (VS1838B / TL1838 / HS0038 / TSOP38238 — interchangeable)
- Protocol: NEC
- Address: `0x00FF`

![Board](./m515-actual.jpg)

## Credit

Code table sourced from:
https://devices.esphome.io/devices/generic-remote-receiver/
("cheap 'car mp3' remote", included in some Elegoo kits)

## Setup

- Phone: Redmi Note 11 (built-in IR blaster)
- App: IR Blaster Remote (`org.nslabs.ir_blaster`) — F-Droid / Google Play
- Settings > IR Transmitter > Internal

## Add a Button

1. Remotes tab > Add Button
2. Protocol: NEC
3. Frequency: 38kHz
4. Hex: short form, no leading `00` (e.g. `FFA25D`)
5. Test at 10–30cm, line of sight to receiver dome

## Working Codes

| Button | Hex | Full Code |
|---|---|---|
| Power | `FFA25D` | `0x00FFA25D` |
| Mode | `FF22DD` | `0x00FF22DD` |
| Previous | `FFE01F` | `0x00FFE01F` |
| Next | `FFA857` | `0x00FFA857` |
| Volume Minus | `FF6897` | `0x00FF6897` |
| Volume Add | `FF9867` | `0x00FF9867` |
| Equalizer | `FFC23D` | `0x00FFC23D` |
| Scan Channels | `FF906F` | `0x00FF906F` |
| Mute | `FFE21D` | `0x00FFE21D` |

All: NEC, 38kHz, address `0x00FF`.

![Remote](./screenshot1.png)

## Untested / Not Found

- Play/Pause not confirmed. Candidates to try: `FF02FD`, `FF629D`, `FFB04F`.

## Fallback

If a different board doesn't match this table: use IR Blaster Remote's Signal Tester (NEC, hex prefix `00`/`40`/`80`/`FF`, watch for reaction).

## Files

- `README.md`
- `m515-actual.jpg` — board photo
- `screenshot1.png` — finished remote
