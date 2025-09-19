# coTfsSetReportBehaviour

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSetReportBehaviour( dword reportSetting );
```

## Description

With this function, the report behavior of the node layer can be set. In contrast to the function [coTfsSetFailControl](CAPLfunctionCoTfsSetFailControl.md) outputs were not interchanged but enabled/disabled selectively.

The parameter **reportSetting** is a bit field and sets the behavior of the node layer. Per default all outputs are enabled (**reportSettings=0x3FFFDFFF**).

## Parameters

- **reportSetting**: Bit field to set the report behavior:
  - bit 0: output of the initial message of each test
  - bit 1: output of the standard Test step messages
  - bit 2: output of the Test passed message
  - bit 3: output of the Test failed message
  - bit 4: output of warnings
  - bit 5: information messages
  - bit 6: expected messages, if a test fails the report contains a summary of expected messages
  - bit 7: message data (transferred data and used masks)
  - bit 8: all SDO abort codes that are not sent from the current DUT
  - bit 9: all received SDO abort codes including the DUT ones
  - bit 12: all received emergency codes
  - bit 13: SDO protocol specific control bits
  - bit 19: information about injected or replaced messages
  - bit 20: output of generic monitor messages
  - bit 21: output of generic monitor warning messages
  - all other bits are reserved

**Note**: If the output is disabled for test step pass/fail (bit 2 and bit 3), the verdict of the test function is not set by the CANopen® test module. It shall be set by the user test.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
[globals section]
const kTestStepInit    = 0x00000001;
const kTestStep      = 0x00000002;
const kTestStepPass    = 0x00000004;
const kTestStepFail    = 0x00000008;
const kTestStepWarning   = 0x00000010;
const kTestStepResume   = 0x00000020;
const kTestStepInfo    = 0x00000040;
const kTestStepNone    = 0x00000000;
const kTestStepDefault = 0x3FFFDFFF;
const kTestStepAll = 0x3FFFDFFF;

[test case]
coTfsSetReportBehaviour( kTestStepAll );
```
