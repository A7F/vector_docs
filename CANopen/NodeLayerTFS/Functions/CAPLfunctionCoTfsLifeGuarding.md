[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLifeGuarding.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsLifeGuarding**

# coTfsLifeGuarding (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
long coTfsLifeGuarding( dword guardTime, dword retryFactor, dword tolerance );
```

## Description

The test sets the guard time and retry factor objects in the DUT (Device Under Test). After that, 20 guarding remote frames are sent to the target device which must respond to all queries within the `guardTime+tolerance`.

Afterwards the sending of the remote frames is stopped. It is waited for the corresponding emergency message (EMCY code = 0x8130, Error Register = 0x11) before the values of the guard time and retry factor objects are reset.

## Parameters

- **guardTime**: Guard time in milliseconds.
- **retryFactor**: Retry factor
- **tolerance**: Permitted time deviation of the target device in milliseconds. It is recommended that you use an even value. The tolerated time frame within which a message is still accepted is: x - (delta/2) <= x <= x + (delta/2)

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
if ( coTfsLifeGuarding( 500, 5, 50) != 1) {  // guard time, retry Factor, tolerance
  write("lifeguarding failed");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)