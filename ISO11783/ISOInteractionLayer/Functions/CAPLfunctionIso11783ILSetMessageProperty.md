[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILSetMessageProperty.md)

# Iso11783IL_SetMessageProperty

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_SetMessageProperty

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_SetMessageProperty( dbMsg msg, char propertyName[], long propertyValue);
```

## Description

This function sets the internal property of a message.

## Parameters

- **msg**: Message name as defined in the database
- **propertyName**: Name of property to be set
  - **Value**: "MessageCounterToContinue"
  - **Description**: Defines the next value of the intern message counter that will be sent. Applicable for the PGNs 0, 1024, 2816, 61469 and 61483 only (see [Message Checksum and Message Counter](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILErrorDetection.md)). Valid values for propertyValue are 0 to 7 (PGN = 0) or 0 to 15 (all other applicable PGNs).
- **propertyValue**: New value to be set for the property

## Return Values

- **0**: Success (property has been set successfully)
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
if (Iso11783IL_SetMessageProperty(TSC1, "MessageCounterToContinue", 12) < 0)
{
  write("Can’t set message property ‘MessageCounterToContinue‘");
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
