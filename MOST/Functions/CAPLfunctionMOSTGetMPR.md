[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetMPR.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetMPR

# mostGetMPR

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long mostGetMPR (long channel);
```

## Description

This function returns the "Maximum Position Register (MPR)" value of the MOST hardware chip connected to the channel. If the loop is stable, MPR represents the number of devices with opened bypass.

## Parameters

- **channel**: Channel of the connected MOST hardware.

## Return Values

- **\> 0**: MPR value
- **\<= 0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [OnMostMPR](../EventProcedures/CAPLfunctionOnMOSTMPR.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
