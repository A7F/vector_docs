[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetSpyCtrl.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetSpyCtrl, mostSetSpyAsync, mostSetSpyEthPkt

# mostSetSpyCtrl, mostSetSpyAsync, mostSetSpyEthPkt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostSetSpyCtrl(long channel, long mode);`
- `long mostSetSpyAsync(long channel, long mode);`
- **MOST150**: `long mostSetSpyEthPkt(long channel, long mode);`

## Description

Spy mode is activated (mode = 1) or deactivated (mode = 0) for the **Control**, **Asynchronous** or **Ethernet** transmission channel using these functions.

## Parameters

- **channel**: Channel of the connected interface
- **mode**:
  - `0`: Spy inactive
  - `1`: Spy active

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).  
For MOST network interfaces that do not support a Spy mode, the error code **kMostWrongHWType** is returned.

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostGetSpyCtrl, mostGetSpyAsync, mostGetSpyEthPkt](CAPLfunctionMOSTGetSpyCtrl.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
