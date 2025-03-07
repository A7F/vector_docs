[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSendSamplingTestHeader.md)

**CAPL Functions** » **LIN** » **linSendSamplingTestHeader**

# linSendSamplingTestHeader

**Valid for**: CANoe DE

## Function Syntax

```
long linSendSamplingTestHeader(dword startBitLengthInMicSec);
```

## Description

Sends a slave response header with the start bit of the id byte set to the specified length.

## Parameters

- **startBitLengthInMicSec**: The length of the start bit in microseconds. The first data bit will be adjusted to ensure that the start bit and the first data bit have a total length of two bit times.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)