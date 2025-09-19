# diagGetErrorString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long diagGetErrorString (long errorCode, char bufferOut[], dword bufferLength)
```

## Description

Retrieves a text describing the error code.

## Parameters

- **errorCode**: Numeric error code
- **bufferOut**: Output buffer
- **bufferLength**: Output buffer size

## Return Values

Length of the text in **bufferOut**.

## Example

```plaintext
on key 't'
{
  long retValue;
  char buffer[200];
  if (0 > (retValue=diagSetTarget("UDS_Diagnostic_Services"))) 
  {
    diagGetErrorString(retValue, buffer, elcount(buffer));
    write("Error: %s", buffer);
  }
}
```
