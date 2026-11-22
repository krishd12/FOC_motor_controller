STM32F405RGT7TR — KiCad symbol and footprint

INSTALL (KiCad 9 or newer)
1. Extract this ZIP to a permanent folder.
2. Preferences > Manage Symbol Libraries > Add existing library:
   select STM32F405RGT7TR.kicad_sym.
3. Preferences > Manage Footprint Libraries > Add existing library:
   select STM32F405_Custom.pretty. Keep nickname STM32F405_Custom
   so the symbol's assigned footprint resolves correctly.
4. Place STM32F405RGT7TR in the schematic and update PCB from schematic.

SYMBOL
Single unit, grouped two-column layout inspired by the supplied Altium image.
PA/PC left, PB/PH/PD and controls right; supplies above, grounds below.
All 64 pins are visible and separately connectable, including all VDD/VSS pins.
Oscillator pins are PH0/PH1 for this part (not PD0/PD1 in the reference).
Colors follow your KiCad theme; the symbol uses background body fill.
Alternate pin functions and electrical types retained from KiCad's
STM32F405RGTx symbol; separated VDD/VSS pins are power inputs. VCAP pins retain the library's passive type.

FOOTPRINT
LQFP64: body 10 x 10 mm, lead span 12 x 12 mm, pitch 0.5 mm.
64 SMD pads; no exposed pad. Standard KiCad land pattern:
pads 1.55 x 0.30 mm (rotated on top/bottom), row centers +/-5.675 mm.
Includes solder paste/mask, silkscreen pin-1 marker, fabrication and courtyard.
Optional 3D model resolves from the separately installed KiCad 9 model library.

SOURCES / ATTRIBUTION
ST STM32F405xx/407xx datasheet DS8626 Rev 12 (March 2026),
Figure 12 (p.43) and LQFP64 mechanical data Table 92 (p.170):
https://www.st.com/resource/en/datasheet/stm32f405rg.pdf
Symbol adapted from official KiCad MCU_ST_STM32F4:STM32F405RGTx.
Footprint adapted from official KiCad Package_QFP:LQFP-64_10x10mm_P0.5mm.
KiCad library content: CC-BY-SA-4.0 with KiCad libraries exception.
https://www.kicad.org/libraries/license/
https://creativecommons.org/licenses/by-sa/4.0/
Modifications: custom symbol placement/names and part-specific metadata.
The KiCad exception permits use in electronic designs without requiring
those designs to inherit this license. See linked license for full terms.

Validation: 64 unique symbol pins match 64 unique footprint pads;
numbering compared with ST LQFP64 top-view pinout. Files parsed by KiCad.
