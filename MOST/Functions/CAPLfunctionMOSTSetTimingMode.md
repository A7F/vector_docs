[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetTimingMode.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetTimingMode

# mostSetTimingMode

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long mostSetTimingMode(long channel, long mode);
```

## Description

This function configures the MOST hardware as a Timing Master (mode = 1) or Timing Slave (mode = 0).

**MOST25**: For further information on Master/Slave switchover functionality see also the description of the MTR bit in the Transceiver Control Register of the OS8104.

**MOST50/150**: Switching from Slave to non-static Master does not wake the network automatically. Use [mostWakeup](CAPLfunctionMOSTWakeup.md) to start the network.

**Note**: If the bypass is closed (see [mostSetAllBypass()](CAPLfunctionMOSTSetAllBypass.md)) this function has no effect until the bypass is opened.

## Parameters

- **channel**: Channel of the connected interface
- **mode**: 
  - `0`: Slave
  - `1`: Master

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostGetTimingMode](CAPLfunctionMOSTGetTimingMode.md) • [OnMostTimingMode](../EventProcedures/CAPLfunctionOnMOSTTimingMode.md) • [mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetMasterMode](CAPLfunctionMOSTSetGetMasterMode.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)