CMOS_Inverter KiCad Project Bundle
=================================

Files:
- CMOS_Inverter.kicad_pro  : KiCad project metadata (for KiCad 9.0.4)
- CMOS_Inverter.kicad_sch  : KiCad schematic file (S-expression)
- CMOS_Inverter.cir        : NGSpice netlist for simulation
- CMOS_inverter_professional.png : High-quality schematic PNG
- CMOS_Inverter.proj       : Simple project descriptor

How to use:
1. Open KiCad (9.0.4) and open a new project, or simply open the .kicad_sch file in Eeschema.
2. If symbol libraries are missing, KiCad will show placeholders — replace with your library symbols (NMOS/PMOS/power sources).
3. To simulate in ngspice, either run the .cir netlist directly with ngspice, or recreate the schematic in Eeschema and set up simulation commands in the Schematic Editor.
4. For foundry-accurate simulation, include SG13G PDK model files and modify MOSFET symbol attributes to reference those models.

Notes:
- The .kicad_sch is a best-effort file and may require symbol mapping to your local KiCad libraries.
- If you want a fully working KiCad project with correct library references, upload your KiCad library files or tell me which library names to use and I will adjust the schematic accordingly.