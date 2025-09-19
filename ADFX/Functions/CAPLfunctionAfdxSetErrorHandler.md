# AfdxSetErrorHandler

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxSetErrorHandler( char callback[] );
```

## Description

Use this function to register a [CAPL callback](../EventProcedures/CAPLfunctionOnAfdxError.md) to handle AFDX error events.

## Parameters

- **callback**: Name of CAPL callback.

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

Node **System – PreStart** in CAPL Browser

```plaintext
on preStart
{
  AfdxSetErrorHandler( "OnAfdxError");
}
```

Node **Callback Function** in CAPL Browser

```plaintext
void OnAfdxError( int64 time, long channel, long errorType, char errorText[], char errorAttributes[])
{
  if (errorType == AfdxError)
  {
    write( "<%NODE_NAME%> Afdx Error on channel %d: %s", channel, errorText);
  }
}
```
