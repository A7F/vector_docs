[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSetFailControl.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSetFailControl**

# coTfsSetFailControl

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSetFailControl( dword controlValue );
```

## Description

Determines the behavior of CANopen test feature set tests. The entries in the test report can be switched with this function, that is, a test that in the default setting 0 has passed also receives the note "passed" in the test protocol. Conversely, a failed test receives the note "failed".

The call of this function with the parameter 1 reverses the behavior. If the device should pass a test, failed is in the test report and vice-versa. This behavior can be used to create a negative test.

After measurement start, the setting 0 is always active.

The return value of the test functions themselves in the CAPL program is never changed, only the protocol is adjusted.

## Parameters

- **controlValue**
  - 0: normal behavior (default)
  - 1: inverted behavior
  - 2: the test case is not marked with pass or fail in the test report, the user must ensure the corresponding entries himself

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSetFailControl (1); // invert report behavior

// run some negative tests

coTfsSetFailControl (0); // switch back to normal behavior
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)