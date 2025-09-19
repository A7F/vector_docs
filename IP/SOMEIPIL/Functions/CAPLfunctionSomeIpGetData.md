[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetData.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpGetData**

# SomeIpGetData

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword SomeIpGetData(dword messageHandle, dword bufferLength, char buffer[]); // form 1`
- `dword SomeIpGetData(dword messageHandle, dword bufferLength, byte buffer[]); // form 2`
- `dword SomeIpGetData(dword messageHandle, dword bufferLength, struct buffer[]); // form 3`

## Description

This function can be used to query the raw data of a SOME/IP message.

## Parameters

- **messageHandle**: Handle of the received SOME/IP message (see [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md))
- **bufferLength**: Size of the buffer in bytes
- **buffer**: Data are copied to this buffer

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Number of copied bytes

## Example

```c
void OnSomeIpMessage(DWORD messageHandle)
{
  BYTE buffer[200];
  BYTE bufferMsg[200];
  DWORD count;
  DWORD size;
  CHAR dest[200];

  count = 0;

  // Check if message is a non Service Discovery message
  if(SomeIpGetMessageId(messageHandle) != 0xFFFF8100)
  {
    // Check if message is a Notification message
    if(SomeIpGetMessageType(messageHandle) == 0x2)
    {
      write("SOME/IP Notification message received!\n");

      // write whole message data (including header and payload) to write window
      size = SomeIpSerializeMessage(messageHandle, elcount(bufferMsg), bufferMsg);
      write("Message size: %d", size);
      snprintf(dest, elcount(dest), "%s", "");
      for(count = 0; count < size; count++)
      {
        snprintf(dest, elcount(dest), "%s %02x", dest, bufferMsg[count]);
      }
      write("Serialized Message: %s", dest);

      // write only message payload to write window
      size = SomeIpGetData(messageHandle, elcount(buffer), buffer);
      write("Payload size: %d", size);
      snprintf(dest, elcount(dest), "%s", "");
      for(count = 0; count < size; count++)
      {
        snprintf(dest, elcount(dest), "%s %02x", dest, buffer[count]);
      }
      write("Serialized Payload: %s\n", dest);
    }
  }
}
```

[See Also](javascript:void(0);)
