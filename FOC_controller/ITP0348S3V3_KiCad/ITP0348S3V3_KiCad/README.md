# XP Power ITP0348S3V3 — KiCad library

Files target KiCad 7 and newer (native S-expression libraries).

## Install
1. Extract this ZIP to a permanent directory.
2. KiCad: Preferences > Manage Symbol Libraries > add existing library; select XP_Power.kicad_sym. Use nickname XP_Power.
3. Preferences > Manage Footprint Libraries > add existing library; select the XP_Power.pretty directory. Use nickname XP_Power.
4. Place XP_Power:ITP0348S3V3. Its footprint property already points to XP_Power:XP_Power_ITP0348S3V3_SIP6.
5. Update the PCB from the schematic.

## Pin mapping
| Pin | Function | Pad X (mm) | Pad Y (mm) |
|---|---|---:|---:|
| 1 | -Vin | 0 | 0 |
| 2 | +Vin | 2.54 | 0 |
| 3 | Remote On/Off | 5.08 | 0 |
| 4 | NC / physically absent in single-output drawing | no pad | no pad |
| 5 | +Vout | 10.16 | 0 |
| 6 | -Vout | 12.70 | 0 |

Pin 4 is omitted from both symbol and footprint because the single-output mechanical drawing shows no lead at that position. Do not renumber the output pins.

## Source and revision
Manufacturer: https://www.xppower.com/storage/portals/0/pdfs/SF_ITP.pdf
Downloaded 2026-10-17; printed revision 11 November 2025, page 4.
The downloaded current PDF differs from an older web-cached copy in numbering and dimensions. This library follows the current PDF pin-connections table and single-output mechanical drawing. Some application-circuit illustrations in that same PDF show inconsistent numbering; do not use them to assign pins. Check the supplied module and its applicable manufacturer revision before PCB fabrication.

## Footprint geometry and design choices
Top/component view, pin 1 at the origin. The printed face is on the positive-Y side, facing toward the viewer when reading pins left-to-right. The body extends mostly in negative Y.
- 2.54 mm pitch; pin 4 position skipped; pin 1 to pin 6 span 12.70 mm.
- Fabrication outline uses the larger plan-view envelope: 17.52 x 10.20 mm. The elevation drawing also quotes 17.0 mm; larger envelope used conservatively.
- Pin 1 offset from left edge: 2.41 mm; pin row offset from printed-face edge: 2.38 mm.
- Body bounds relative to pin 1: X -2.41 to +15.11; Y -7.82 to +2.38 mm.
- Through holes: 1.30 mm finished diameter; copper pads 2.10 mm. These are conservative author-selected land dimensions, not a manufacturer recommended land pattern. They allow clearance for the stated 0.50 +/-0.05 mm pins and +/-0.35 mm pin-pitch tolerance. Confirm drill capability and fit with your fabricator/module.
- Square pin-1 pad plus silk dot. F.Fab, F.SilkS and F.CrtYd included.
- Courtyard adds at least 0.75 mm beyond nominal body bounds, accounting for stated +/-0.5 mm case tolerance and assembly clearance.
- No 3D model is included.

## Symbol and electrical notes
Input pins are power_in, output pins power_out, remote input is input. Keep input and output return nets distinct if galvanic isolation is required. Remote pin may be left open for normal operation; mark intentionally unconnected in the schematic if unused. It is a current-driven remote input, not a generic 3.3V logic enable: consult the datasheet before driving it.

## Validation
S-expression syntax, unique pin numbers, symbol/footprint correspondence, pad spacing, body dimensions and drill clearance checked programmatically. Preview is generated from the actual library geometry. KiCad is not installed in the creation environment, so native KiCad import/ERC/DRC was not run. Open both libraries in your KiCad version and check orientation against the physical part before manufacturing.
