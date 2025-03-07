[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsGuarding.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsGuarding**

# coTfsGuarding (Level 3)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsGuarding( void );
```

## Description

This test checks the [life guarding](CAPLfunctionCoTfsLifeGuarding.md) and [node guarding](CAPLfunctionCoTfsNodeGuarding.md) functionality of the node.

The [life guarding](CAPLfunctionCoTfsLifeGuarding.md) tests are executed with the following parameters:

- guard time: 1s, 500ms, 500ms
- retry factor: 3, 5, 3
- permissible tolerance: 10%, 10%, 5%

After that, the [node guarding](CAPLfunctionCoTfsNodeGuarding.md) tests with decreasing time tolerances are executed to check the response time. The permissible deviations are 500 ms, 10 ms, 50 ms, and 26 ms. To pass the test, all individual test cases must be run through successfully.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if (coTfsGuarding() != 1) {
  write("guarding test failed");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)