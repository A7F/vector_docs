# AfdxSetSignalReal

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxSetSignalReal( long packet, char signalName[], float value, long fdsStatus ); // form 1
long AfdxSetSignalReal( long packet, long offset, long isDouble, float value ); // form 2
```

## Description

This function sets the value of a 32-bit or 64-bit float signal (IEEE 754).

## Parameters

- **packet**: handle of the message
- **signalName**: name of the signal
  - **Note**: The signal and its message need to be defined in the assigned DBC file.
- **offset**: The offset value points to the float signal in the AFDX payload area.
- **isDouble**:
  - 0: set 32-bit float value
  - 1: set 64-bit float value
- **value**: new float value
- **fdsStatus**:
  - 255: The status is not updated
  - [valid status enumeration](../../../CANoeCANalyzer/AFDX/afdxBasics/afdxFunctionalDataSet.md): The functional status is updated with this value.

## Return Values

0 or [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

—

