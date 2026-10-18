# AMC131M03DFMR — KiCad symbol and footprint

## Installation (KiCad 7 and newer)
1. Extract ZIP to a permanent folder.
2. Preferences > Manage Symbol Libraries > Add existing: select TI_Isolated_ADC.kicad_sym and use nickname TI_Isolated_ADC.
3. Preferences > Manage Footprint Libraries > Add existing: select TI_Isolated_ADC.pretty and use nickname TI_Isolated_ADC.
4. Place TI_Isolated_ADC:AMC131M03DFMR. Its footprint property is preassigned.

## Source
TI AMC131M03 datasheet SBAS994B, Rev B, September 2023; downloaded 2026-10-18.
https://www.ti.com/lit/ds/symlink/amc131m03.pdf
Pin mapping: Table 5-1, page 3.
DFM0020A mechanical/land drawing: 4225640/A, January 2020, appended to datasheet.
DFM is the 20-pin wide-body SOIC package; final R specifies tape-and-reel packing.

## Symbol
Single unit, analog/isolated-side pins on left, MCU-side pins on right. Dashed center line indicates the isolation boundary. All 20 pins visible. AIN12N is shared by channels 1 and 2; AIN0N is separate. Active-low names have overbars. Reference designator U; 1.27mm text, 2.54mm pin grid. Power output pins are flagged as such; DCDC_CAP is passive because it is the internally generated capacitor node. AIN2P/GPO is bidirectional because it is configurable; normally use as analog input for three-channel measurement.

| Pin | Function |
|---|---|
| 1 | DCDC_OUT |
| 2 | DCDC_HGND |
| 3 | HLDO_IN |
| 4 | HLDO_OUT |
| 5 | HGND |
| 6 | AIN2P/GPO |
| 7 | AIN12N |
| 8 | AIN1P |
| 9 | AIN0P |
| 10 | AIN0N |
| 11 | SYNC/RESET, active low |
| 12 | DOUT |
| 13 | DVDD |
| 14 | DCDC_CAP |
| 15 | DGND |
| 16 | DRDY, active low |
| 17 | CLKIN |
| 18 | SCLK |
| 19 | CS, active low |
| 20 | DIN |

## Footprint geometry
20 SMD pads, 2.10 x 0.60mm, pitch 1.27mm, row center separation 9.70mm. Pad corner radius 0.05mm follows TI drawing. Nominal molded body 7.50 x 12.83mm, max height 3.55mm. Pin 1 top left, counting counter-clockwise in top view. No exposed/thermal pad. F.Fab chamfer and silk marker identify pin 1. Courtyard +/-6.15mm in X, +/-6.75mm in Y; author-selected courtyard beyond max body and copper bounds. Solder-mask/paste openings use board defaults. No 3D model.

## Circuit and layout reminders
Connect DCDC_OUT to HLDO_IN; connect DCDC_HGND to HGND. Add the decoupling and ferrite network specified in datasheet section 9.3; this library contains the IC only. HGND and DGND are on opposite sides of the isolation barrier. Keep the isolation clearance area free of conductive material on all layers according to section 9.4 and your required isolation spacing; the footprint does not impose a blanket copper keepout. AIN12N is a signal input, not a supply ground. CLKIN is required separately from SPI SCLK. Check delta-sigma filter delay against PWM current sampling before finalizing an FOC design.

## Validation
Pin table cross-checked against TI; native S-expression syntax, all 20 unique symbol/footprint pin numbers, 1.27mm pitch, 9.70mm row spacing and 2.1x0.6mm pads checked programmatically. Preview generated from library geometry and inspected. Native KiCad import/ERC/DRC could not be run because KiCad is not installed. Inspect the imported libraries in your KiCad version before PCB fabrication.
