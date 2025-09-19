[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetSyncSpdifMode.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetSyncSpdifMode

# mostGetSyncSpdifMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2610/VN2640.

## Function Syntax

`long mostGetSyncSpdifMode(long channel);`

## Description

Gets the timing mode for the S/PDIF signal.

## Parameters

- **channel**: Channel of the connected interface.

## Return Values

- **0**: S/PDIF slave
- **1**: S/PDIF master
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostSetSyncSpdif](CAPLfunctionMOSTSetSyncSpdif.md) • [mostSetSyncSpdifMode](CAPLfunctionMOSTSetSyncSpdifMode.md) • [mostSetSyncSpdifLock](CAPLfunctionMOSTSetSyncSpdifLock.md) • [mostSetClockSource](CAPLfunctionMOSTSetClockSource.md) • [mostGetClockSource](CAPLfunctionMOSTGetClockSource.md) • [mostSetSyncAudio](CAPLfunctionMOSTSetSyncAudio.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
