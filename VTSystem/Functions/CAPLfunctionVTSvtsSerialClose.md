[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSerialClose.md)

**CAPL Functions** » **VT System** » **vtsSerialClose**

# vtsSerialClose

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long vtsSerialClose (char Target[]);
```

## Description

Closes the serial port of the VT System channel that is specified by the system variable namespace.

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.

## Example

See example [vtsSerialConfigure](CAPLfunctionVTSvtsSerialConfigure.md)

[SerialClose](CAPLfunctionVTSSerialClose.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)