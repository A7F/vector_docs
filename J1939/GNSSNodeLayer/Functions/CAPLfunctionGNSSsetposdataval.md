[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSsetposdataval.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSSetPosDataVal

# GNSSSetPosDataVal

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSSetPosDataVal(dword fixSID, dword systemAndMethod, dword integrity, dword numOfSVs, dword hdop, dword pdop, dword geoSeparation, dword numOfRefStat, dword refStations[])
```

## Description

This function can be used to change values of parameter group "GNSS Position Data" (PGN 129029) which are not modified by the simulation automatically.

**Note**: The same settings can be made via [node attributes](../../../../CANoeCANalyzer/J1939/gnssNL/gnssNLDbAttributes.md) in the used database.

## Parameters

- **fixSID**: 1 if fix sequence ID (255) has to be used, else 0
- **systemAndMethod**: the first 4 bit specifies the system type, the upper 4 bit the GNSS Method
- **integrity**: integrity
- **numOfSVs**: number of visible satellites
- **hdop**: horizontal dilution of precision
- **pdop**: position dilution of precision
- **geoSeparation**: geoidal separation
- **numOfRefStat**: number of reference stations
- **refStations**: array of reference stations, every station is specified by 4 bytes (Bit 0-3: Type, Bit 4-15: ID, Bit 16-31: Ages of DGNSS Corrections)

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
dword refSta[2];
refStation[0] = 0x11110010;
refStation[1] = 0x22220020;
GNSSSetPosDataVal(0,0x20,1,4,21,54,763,2,refSta);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
