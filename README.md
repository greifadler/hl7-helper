# HL7 Helper

A single-file HL7 v2 message inspector. Open `index.html` in any browser: it runs entirely locally, needs nothing installed, and doesn't send or store any data. The interface is available in German and English.

## Analyze

- Paste a message. Hover over any value to see its path and field name (e.g. `OBX[2]-3.2 · Observation Identifier › Text`).
- Click a value to see its full breakdown (segment › field › component › subcomponent), data type, raw and decoded value, and every field of the segment.
- **HL7 version:** taken from MSH-12 automatically or chosen manually (2.1–2.9). Data types follow the version (e.g. CE → CWE from 2.6, TS → DTM from 2.7).
- Shows timestamps as readable dates, looks up HL7 table codes and decodes escape sequences.
- Path search: `PID-5.1`, `OBX[2]-5`, `MSH9.2`
- Table view of all populated fields (filterable) and a JSON export
- Download embedded files from OBX-5 (type ED)

## Compare

- Matches segments between two messages, even when segments are inserted or missing
- Highlights differences down to the component level, with a clickable list of differences
- Can ignore chosen fields (default: `MSH-7`, `MSH-10`)

## DACH support

Region is detected from MSH-17, MSH-12 or the OIDs in the message, or can be set manually.

| | Identifier | OID | Check |
|---|---|---|---|
| DE | Krankenversichertennummer (KVNR) | 1.2.276.0.76.4.8 | check digit |
| DE | Institutionskennzeichen (IK) | 1.2.276.0.76.4.5 | check digit |
| DE | Lebenslange Arztnummer (LANR) | 1.2.276.0.76.4.16 | check digit |
| DE | Betriebsstättennummer (BSNR) | 1.2.276.0.76.4.17 | format |
| AT | Sozialversicherungsnummer (SVNR) | 1.2.40.0.10.1.4.3.1 | check digit |
| CH | AHV-Nummer (AHVN13) | 2.16.756.5.32 | check digit |
| – | GLN | 2.51.1.3 | check digit |

Identifiers are recognized by OID (assigning authority), by identifier type (e.g. `LANR` in XCN-13 as recommended by HL7 Deutschland) or by format.

Also included:
- the ZBE segment (IHE PAM / HL7 Deutschland / HL7 Austria)
- the HL7 Austria Z-segments ZAC, ZTE and ZNG
- the HL7 Austria value set for administrative gender (D, I, O, X)
- German translations of the common HL7 tables

Field names cover the common HL7 v2.5 segments (MSH, EVN, PID, PD1, NK1, PV1, PV2, ORC, OBR, OBX, NTE, AL1, DG1, PR1, IN1, MSA, ERR, MRG, SPM, TXA, ROL, TQ1, SCH, AIS, FT1). All sample messages contain synthetic data only.
