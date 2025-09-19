[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetSBC.md)

**CAPL Functions** » **MOST** » **mostSetSBC**

# mostSetSBC

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long mostSetSBC (long channel, long sbcvalue);
```

## Description

This function sets the "Synchronous Bandwidth Control (SBC) Register" of the MOST hardware chip to the given value. The function is only practically applicable if the hardware connected to the channel is in master mode. The newly set value is only accepted once a "DeAllocate" message re-releases all synchronous channel assignments.

## Parameters

- **channel**: Channel of the connected MOST hardware
- **sbcvalue**: New SBC register value. Values between 0 and 15 are permitted.

## Return Values

—

## Example

—

[mostGetSBC](CAPLfunctionMOSTGetSBC.md) • [OnMostSBC](../EventProcedures/CAPLfunctionOnMOSTSBC.md) • [mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostSetCorrectStartupSBC](CAPLfunctionMOSTSetCorrectStartupSBC.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
