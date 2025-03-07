[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINResetManualChecksum.md)

**CAPL Functions** » **LIN** » **linResetManualChecksum**

# linResetManualChecksum

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void linResetManualChecksum(linFrame linFrame);
```

## Description

Sets the correct checksum of a LIN frame, whose checksum has been changed by using [linSetManualChecksum()](CAPLfunctionLINSetManualChecksum.md) function. The checksum is calculated using the frame data.

## Parameters

- **linFrame**: LIN frame for which the correct checksum will be used again.

## Return Values

—

## Example

Reset checksum error caused by previously called [linSetManualChecksum()](CAPLfunctionLINSetManualChecksum.md)

```plaintext
...
linFrame MotorControl frmMotorControl;
linResetManualChecksum(frmMotorControl);
output(frmMotorControl); // it is important to call output() to make the changes active
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)