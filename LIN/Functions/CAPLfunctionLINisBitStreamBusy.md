[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINisBitStreamBusy.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linIsBitStreamBusy

# linIsBitStreamBusy

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword linIsBitStreamBusy(); // form 1`
- `dword linIsBitStreamBusy(dword channel); // form 2`

## Description

Queries the current LIN bitstream sending status.

## Parameters

- **channel**: The LIN channel number which will be queried.

## Return Values

Returns **1** if a bitstream is currently being sent, otherwise **0**.

## Example

```c
// Make sure that there is no bitstream sending active before a new transmission is started

if (linIsBitStreamBusy() == 0)
{
  linSendBitStream(data, numberOfBits);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
