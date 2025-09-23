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
