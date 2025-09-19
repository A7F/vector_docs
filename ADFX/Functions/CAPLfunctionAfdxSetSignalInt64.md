# AfdxSetSignalInt64

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxSetSignalInt64( long packet, char signalName[], int64 value, long fdsStatus ); // form 1
long AfdxSetSignalInt64( long packet, long offset, int64 value ); // form 2
```

## Description

This function sets the value of a 64-bit integer signal.

## Parameters

- **packet**: Handle of the message.
- **signalName**: Name of the signal.
  - **Note**: The signal and its message need to be defined in the assigned DBC file.
- **offset**: The offset value points to the 64-bit integer signal in the AFDX payload area.
- **value**: New 64-bit integer value.
- **fdsStatus**:
  - 255: The status is not updated
  - [valid status enumeration](../../../CANoeCANalyzer/AFDX/afdxBasics/afdxFunctionalDataSet.md): The functional status is updated with this value.

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

—

