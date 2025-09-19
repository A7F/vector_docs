# AfdxGetDBAttrAsString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetDBAttrAsString( long msgID, char attrName[], long bufSize, char buffer[]);
```

## Description

Retrieves a message attribute value in string representation from a given message ID.

## Parameters

- **msgID**: Unique message ID as defined in the DBC.
- **attrName**: Name of the [message attribute](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportMessageAttributes.md).
- **bufSize**: Size of the provided buffer to get the value into.
- **buffer**: Buffer which should hold the found value.

## Return Values

- **0**: Success
- **other value**: See [error code](../CAPLfunctionsAFDXErrorCodes.md).

## Example

—
