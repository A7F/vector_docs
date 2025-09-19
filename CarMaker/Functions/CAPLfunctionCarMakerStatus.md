# CarMaker_Status

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_Status();
```

## Description

Retrieves the status of the CarMaker connection.

## Parameters

—

## Return Values

**No connection**

- `0x10`: ApoConnDown
- `0x11`: ApoConnError
- `0x12`: ApoConnTimedout
- `0x13`: ApoConnRejected
- `0x14`: ApoConnDisconnected

**Connection is being built up**

- `0x20`: ApoConnPending

**Connection established**

- `0x40`: ApoConnUp
- `0x41`: ApoConnUnsubscribed
- `0x42`: ApoConnSubscribing
- `0x43`: ApoConnReady
- `0x44`: ApoConnDictChange

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
