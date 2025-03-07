[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPOnPointingEvent.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPOnPointingEvent

# Iso11783OPOnPointingEvent (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783OPOnPointingEvent(dword ecuHandle, long x, long y, dword state);
```

## Description

The function is called by the node layer, if the user clicks into the data mask.

## Parameters

- **ecuHandle**: Handle of the ECU
- **x**: X position [pixel]
- **y**: Y position [pixel]
- **state**:
  - 0: Released (Version >= 3)
  - 1: Pressed (pressed)
  - 2: Held (Version >= 3)

## Return Values

—

## Example

```c
void Iso11783OPOnPointingEvent(dword handle, LONG x, LONG y, dword touchState)
{
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)