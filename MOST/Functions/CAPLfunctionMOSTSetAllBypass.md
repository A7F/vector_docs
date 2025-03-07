[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetAllBypass.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetAllBypass

# mostSetAllBypass

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostSetAllBypass(long channel, long bypassmode);
```

## Description

This command can be used to close the MOST hardware bypass (bypassmode=1) or open it (bypassmode=0). If the bypass is closed the MOST device is invisible to other devices in the ring.

For the functionality of the AllBypass see also the description for the /ABY bit in the Transceiver Control Register of the OS8104.

## Parameters

- **channel**: Channel of the connected interface

## Return Values

- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostGetAllBypass](CAPLfunctionMOSTGetAllBypass.md) • [OnMostAllBypass](../EventProcedures/CAPLfunctionOnMOSTAllBypass.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)