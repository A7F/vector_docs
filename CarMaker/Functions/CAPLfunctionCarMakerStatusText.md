# CarMaker_StatusText

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long CarMaker_StatusText(char buffer[], long bufferSize);
```

## Description

Retrieves a textual representation of the current state.

## Parameters

- **buffer**: Buffer that takes the status text.
- **bufferSize**: Size of the buffer.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
// get the current connection status
connState = CarMaker_Status();

if (gConnectionState != connState)
{
  //get detailed connection Info
  gConnectionState = connState;
  CarMaker_StatusText(connTextBuf, elcount(connTextBuf));

  if((gConnectionState & 0x10) != 0) // NOT connected...
  {
    msgSeverity = 3; // Error
  }
  if((gConnectionState & 0x20) != 0) // connecting...
  {
    msgSeverity = 2; // Warning
  }
  if((gConnectionState & 0x40) != 0) // connected...
  {
    msgSeverity = 1; // Information
  }
  writeLineEx(1, msgSeverity, "CarMaker connection status 0x%lx: \"%s\"", gConnectionState, connTextBuf);
}
```
