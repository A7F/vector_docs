# J1939ILSetMessageProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILSetMessageProperty(dbMsg msg, char propertyName[], long propertyValue); // form 1
long J1939ILSetMessageProperty(dbNode node, dbMsg msg, char propertyName[], long propertyValue); // form 2
```

## Description

This function sets the internal property of a message.

## Parameters

- **msg**: message name as defined in the database
- **propertyName**: name of property to be set
  - **Value**: "MessageCounterToContinue"
  - **Description**: Defines the next value of the intern message counter that will be sent. Applicable for the PGNs 0, 1024, 2816, 61469, and 61483 only (see [Message Checksum and Message Counter](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILErrorDetection.md)). Valid values for propertyValue are 0 to 7 (PGN = 0) or 0 to 15 (all other applicable PGNs).
- **propertyValue**: new value to be set for the property
- **node**: Simulation node to apply the function

## Return Values

- **0**: success (property has been set successfully)
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
if (J1939ILSetMessageProperty(TSC1, "MessageCounterToContinue", 12) < 0)
{
  write("Can’t set message property ‘MessageCounterToContinue‘");
}
```
