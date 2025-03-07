[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestSequenceTtitle.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestSequenceTitle

# TestSequenceTitle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
The title must not contain parenthesis.

## Function Syntax

`TestSequenceTitle (char title[]);`

## Description

The title of a test function is acquired automatically from the test function name in the CAPL program. It can also be set explicitly with the help of this function. The function may only be called within a test sequence and relates then to the respective test sequence.

## Parameters

- **title**: Title of the test sequence.

## Return Values

—

## Example

```plaintext
testsequence CheckLockingOnCrash ()
{
  TestSequenceTitle("Check unlock of central locking system on crash");
  // Initialization of signals
  $CrashDetected = 0;
  $LockState = Locked;
  TestWaitForTimeout(200);
}
```

[TestFunctionTitle](CAPLfunctionTestFunctionTitle.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)