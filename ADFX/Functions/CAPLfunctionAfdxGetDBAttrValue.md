# AfdxGetDBAttrValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
double AfdxGetDBAttrValue( long msgID, char attrName[] );
```

## Description

Retrieves the value of a specific attribute of a dedicated message if the attribute is not of type string.

## Parameters

- **msgID**: Unique message ID as defined in the DBC, for which the attribute should be retrieved.
- **attrName**: Name of the [message attribute](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportMessageAttributes.md).

## Return Values

- **0**: If any error occurs, 0 is returned and the exact error code and text can be retrieved using [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md) and [AfdxGetLastErrorText](CAPLfunctionAfdxGetLastErrorText.md).

## Example

—

