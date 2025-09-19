# `<OnAfdxError>` (Callback)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This callback must be implemented in the CAPL program by the user to use the function [AfdxSetErrorHandler](../Functions/CAPLfunctionAfdxSetErrorHandler.md).

## Function Syntax

```plaintext
void <OnAfdxError> ( int64 timestamp, long channel, long errorType, char[] errorText, char[] errorAttributes );
```

## Description

This callback is called when an AFDX Error Event is received.

## Parameters

- **timestamp**: time stamp of the error event in ns
- **channel**: channel number of the error event
- **errorType**:
  - 0: AfdxError
  - 1: AfdxWarning
  - 2: AfdxInfo
- **errorText**: error text of the error event
- **errorAttributes**: error attributes of the error event
  - The attribute string has the following format: DataType;LineHeader;LineData
  - DataType is
    - S: String
    - I: Integer
    - D: Double

## Return Values

—

## Example

**Node System - preStart in CAPL Browser**

```plaintext
on preStart
{
  AfdxSetErrorHandler( "OnAfdxError");
}
```

**Node Callback Function in CAPL Browser**

```plaintext
void OnAfdxError( int64 timestamp, long channel, long errorType, char errorText[], char errorAttributes[])
{
  if (errorType == AfdxError)
  {
    write( "<%NODE_NAME%> Afdx Error on channel %d: %s", channel, errorText);
  }
}
```
