# SM2T3V3A KiCad symbol and footprint

## Import (KiCad 7 or newer)
1. Extract this archive into a permanent directory.
2. Preferences > Manage Symbol Libraries > Add existing: select ST_TVS.kicad_sym, nickname ST_TVS.
3. Preferences > Manage Footprint Libraries > Add existing: select ST_TVS.pretty, nickname ST_TVS.
4. Place ST_TVS:SM2T3V3A. The footprint is already assigned.

## Symbol size and polarity
Compact standard diode scale matching the supplied schematic reference: connection points 7.62 mm (300 mil) apart, graphic approximately 2.54 mm high; 1.27 mm text. Symbol is unidirectional (the screenshot's SMBJ48CA is bidirectional).
Pin 1 = K/cathode; pin 2 = A/anode. These numeric identifiers are library conventions; ST identifies terminals by K and A.
For a positive 3.3 V rail, cathode goes to +3.3 V and anode to that rail's return. On an isolated converter output, that return is -Vout, not input/power ground.

## Footprint
Source: ST SM2T3V3A datasheet, DocID11738 Rev3, August 2015, Figure 3 on page 4 and polarity illustration on page 1.
https://www.st.com/resource/en/datasheet/sm2t3v3a.pdf
Package: STmite / DO-216AA. The pad shapes follow ST's recommended footprint, not a generic SMB package.
- Pad 1 (cathode) is the small right-hand pad: 1.38 x 0.75 mm, center (2.31, 0).
- Pad 2 (anode) is the large left-hand custom pad: main area 1.82 x 2.03 mm, centered at (0,0), plus a 0.50 x 1.10 mm left extension.
- Copper gap between pads: 0.71 mm.
- Cathode band is on the small-pad side, marked on F.Fab and by a silk bar outside pad 1.
- F.Cu, F.Paste, F.Mask, F.Fab, F.SilkS and F.CrtYd included. No 3D model.
- F.Fab represents the nominal 1.90 x 1.90 mm molded body; placement is centered on the large land. Courtyard includes the full land pattern with at least 0.25 mm clearance and maximum body width.
- Footprint orientation is independent of the schematic: K is left in the default symbol, right in the unrotated footprint. Net mapping is by pin number.

## Use on the 3.3 V rail
3.3 V is the stand-off voltage, not a guaranteed 3.3 V clamp. Datasheet breakdown minimum is 3.6 V at 1 mA, and clamp maximum is 6.8 V at 30 A for a 10/1000 us pulse. Check protection coordination with the load's absolute maximum voltage. This TVS addresses transients; local decoupling and any required filtering/layout measures remain necessary for motor-driver EMI.

## Verification
S-expression syntax, pin/pad correspondence, manufacturer pad dimensions and 0.71 mm copper separation checked programmatically. Preview checked visually. KiCad is unavailable in the generation environment, so native KiCad import/ERC/DRC was not run. Review in your KiCad version before fabrication.
