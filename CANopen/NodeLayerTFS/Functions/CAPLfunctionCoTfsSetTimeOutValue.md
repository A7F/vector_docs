# coTfsSetTimeoutValue

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSetTimeoutValue( dword timeout );
```

## Description

This function sets the general time-out of all test functions, insofar as individual functions do not make a separate parameter available for this. The default value at the start of measurement is 2500 ms. If the value is set to 0, the function waits endlessly.

## Parameters

- **timeout**: Time-out in ms.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSetTimeoutValue (300); // set time-out to 300 ms
```
