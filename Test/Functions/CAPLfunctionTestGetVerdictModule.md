# TestGetVerdictModule

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
long TestGetVerdictModule ();
```

## Description

Returns the current verdict out of the test module.

## Parameters

—

## Return Values

- **0**: pass
- **1**: fail
- **2**: none
- **3**: inconclusive
- **4**: error in test system

## Example

```c
// gets the verdict of the test module and report it in the Write Window
void MainTest()
{
   MyTestCase();
   if (TestGetVerdictModule() == 1)
      Write("State of Test Module: failed.");
   else
      Write("State of Test Module: passed.");
}
```

[TestGetVerdictLastTestCase](CAPLfunctionTestGetVerdictLastTestCase.md)
