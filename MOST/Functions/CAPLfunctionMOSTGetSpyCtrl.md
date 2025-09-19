[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetSpyCtrl.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetSpyCtrl, mostGetSpyAsync, mostGetSpyEthPkt

# mostGetSpyCtrl, mostGetSpyAsync, mostGetSpyEthPkt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostGetSpyCtrl(long channel);` // form 1
- `long mostGetSpyAsync(long channel);` // form 2
- **MOST150**: `long mostGetSpyEthPkt(long channel);` // form 3

## Description

Determines whether Spy mode for the **Control**, **Asynchronous** or **Ethernet** transmission channel is activated (Return value = 1) or deactivated (Return value = 0).

## Parameters

- **channel**: Channel of the connected interface.

## Return Values

- **0**: Spy inactive
- **1**: Spy activated
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetSpyCtrl, mostSetSpyAsync, mostSetSpyEthPkt](CAPLfunctionMOSTSetSpyCtrl.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
