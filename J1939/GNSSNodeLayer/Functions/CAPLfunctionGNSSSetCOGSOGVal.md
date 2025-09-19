[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSSetCOGSOGVal.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSSetCOGSOGVal

# GNSSSetCOGSOGVal

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSSetCOGSOGVal ( dword fixSID, dword cogReference)
```

## Description

This function can be used to change values of the parameter group "COG & SOG, Rapid Update" (PGN 129026) which are not modified by the simulation automatically.

**Note:** The same settings can be made via [node attributes](../../../../CANoeCANalyzer/J1939/gnssNL/gnssNLDbAttributes.md) in the used database.

## Parameters

- **fixSID**: 1 if fix sequence ID (255) has to be used, else 0
- **cogReference**: Course Over Ground (COG) reference
  - possible values:
    - 0: true
    - 1: magnetic
    - 2: error
    - 3: null

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
GNSSSetCOGSOGVal(0, 1);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
