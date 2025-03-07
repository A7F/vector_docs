[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Proj/Functions/CAPLfunctionProjCreate.md)

# Proj_Create

[CAPL Functions](../../CAPLfunctions.md) » [Proj](../CAPLfunctionsProjOverview.md) » Proj_Create

**Valid for**: CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long result;
result = Proj_Create(proj_string);
```

## Description

This function initializes the Proj Access with a proj definition. After this, the methods Proj_TransformToGeo or Proj_TransformToInertial can be used to transform coordinates using the Proj Access.

## Parameters

- **definition : string**  
  The Proj String

## Return Values

- **long**  
  0 if initialization is correct, <>0 otherwise

## Example

```plaintext
long result;

result = Proj_Create("+proj=tmerc +a=6378137 +b=6378137 +lon_0=8.8995026301666247 +x_0=-0 +y_0=-5423575.9170007547 +k=1.0 +units=m +nadgrids=@null +wktext +no_defs");
```

## Availability

- **Since Version**
  - CANalyzer: —
  - CANoe: 17 SP2
  - CANoe4SW: —
  - CANoe4SW SE (Windows): 17 SP2
  - CANoe4SW SE (Linux): —
  - vTESTstudio: 8

- **Restricted To**
  - CANalyzer: —
  - CANoe: —
  - CANoe4SW: —
  - CANoe4SW SE (Windows): —
  - CANoe4SW SE (Linux): —
  - vTESTstudio: —

- **CANalyzer Measurement Setup (Transmit Branch)**
  - CANalyzer: —
  - CANoe: N/A
  - CANoe4SW: N/A
  - CANoe4SW SE (Windows): N/A
  - CANoe4SW SE (Linux): N/A
  - vTESTstudio: N/A

- **CANoe Measurement Setup / CANalyzer Analysis Branch**
  - CANalyzer: —
  - CANoe: —
  - CANoe4SW: N/A
  - CANoe4SW SE (Windows): N/A
  - CANoe4SW SE (Linux): N/A
  - vTESTstudio: N/A

- **CANoe Simulation Setup**
  - CANalyzer: N/A
  - CANoe: ✔
  - CANoe4SW: N/A
  - CANoe4SW SE (Windows): —
  - CANoe4SW SE (Linux): —
  - vTESTstudio: N/A

- **CANoe Communication Setup**
  - CANalyzer: N/A
  - CANoe: ✔
  - CANoe4SW: —
  - CANoe4SW SE (Windows): —
  - CANoe4SW SE (Linux): —
  - vTESTstudio: N/A

- **CANoe Test Setup for Test Modules**
  - CANalyzer: N/A
  - CANoe: ✔
  - CANoe4SW: N/A
  - CANoe4SW SE (Windows): —
  - CANoe4SW SE (Linux): —
  - vTESTstudio: N/A

- **CANoe Test Setup for Test Units**
  - CANalyzer: N/A
  - CANoe: ✔
  - CANoe4SW: —
  - CANoe4SW SE (Windows): —
  - CANoe4SW SE (Linux): —
  - vTESTstudio: N/A

- **32-Bit**
  - CANalyzer: —
  - CANoe: ✔
  - CANoe4SW: —
  - CANoe4SW SE (Windows): —
  - CANoe4SW SE (Linux): N/A
  - vTESTstudio: N/A

- **64-Bit**
  - CANalyzer: —
  - CANoe: ✔
  - CANoe4SW: —
  - CANoe4SW SE (Windows): —
  - CANoe4SW SE (Linux): —
  - vTESTstudio: N/A

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)