# HL7 Helper

A single-file, offline HL7 v2 message inspector. Open `index.html` in any browser. There is nothing to install, and no data leaves your machine.

## Features

**Analyze**
- Paste a message. Hover over any value to see its path and name (e.g. `OBX[2]-3.2 · Observation Identifier › Text`).
- Click a value to see the full breakdown (segment › field › component › subcomponent), its data type, the raw and decoded value, and every field of the segment.
- Reads timestamps as dates, looks up HL7 table codes (sex, patient class, result status, abnormal flags, …) and decodes escape sequences.
- Path search: `PID-5.1`, `OBX[2]-5`, `MSH9.2`
- Filterable field list and a JSON export
- Download embedded files from OBX-5 (type ED)

**Compare**
- Matches segments between two messages, even when segments are added or missing
- Highlights differences down to the component level, with a clickable list of differences
- Can ignore chosen fields (default: `MSH-7`, `MSH-10`)

Field names cover the common HL7 v2.5 segments (MSH, EVN, PID, PD1, NK1, PV1, PV2, ORC, OBR, OBX, NTE, AL1, DG1, PR1, IN1, MSA, ERR, MRG, SPM, TXA, ROL, TQ1, SCH, AIS, FT1) plus the German ZBE segment.
