[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINResetRespBaudrate.md)

**CAPL Functions** » **LIN** » **linResetRespBaudrate**

# linResetRespBaudrate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long linResetRespBaudrate(long frameId);
```

## Description

Resets a response baudrate for a specified frame to the master baudrate.

## Parameters

- **frameId**: The identifier of the frame for which the response baudrate will be reset.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linSetRespBaudrate](CAPLfunctionLINSetRespBaudrate.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)