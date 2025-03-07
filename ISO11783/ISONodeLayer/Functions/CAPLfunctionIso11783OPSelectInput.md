[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPSelectInput.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPSelectInput

# Iso11783OPSelectInput

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long Iso11783OPSelectInput( dword ecuHandle, dword objectID, dword select );
```

## Description

The function selects an input object. A **Select Input** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **objectID**: Object ID of an input object
- **select**:
  - 0: no input object shall be selected (i.e. focus is removed)
  - 1: select input object
  - 2: open input object for user input (only version >= 3)

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```c
Iso11783OPSelectInput( handle, 1200, 1 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)