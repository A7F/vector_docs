[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetManualChecksum.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetManualChecksum

# linSetManualChecksum

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void linSetManualChecksum(linFrame linFrame, byte csValue);
```

## Description

Sets a checksum (that is usually not a correct one) for a LIN frame.

## Parameters

- **linFrame**: LIN frame for which a checksum will be set.
- **csValue**: The checksum value to be set.

## Return Values

—

## Example

```plaintext
...
linFrame MotorControl frmMotorControl;
linSetManualChecksum(frmMotorControl, 0x1A);
output(frmMotorControl); // it is important to call output() to make the changes active
```

[linResetManualChecksum](CAPLfunctionLINResetManualChecksum.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
