[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPOnSelectInput.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPOnSelectInput

# Iso11783OPOnSelectInput (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783OPOnSelectInput( dword ecuHandle, dword objectID, dword what );
```

## Description

The function is called by the node layer, if an input object is selected.

## Parameters

- **ecuHandle**: Handle of the ECU
- **objectID**: Object ID of the selected input object
- **what**:
  - 0: input object is not selected
  - 1: input object is selected
  - 2: input object is opened

## Return Values

—

## Example

```c
void Iso11783OPOnSelectInput( dword handle, dword objectID, dword what )
{
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)