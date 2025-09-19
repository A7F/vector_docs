# DtiSend

Valid for: CANoe DE

## Function Syntax

```plaintext
long DtiSend(dword pipeHandle, ethernetPacket packet, int64 timeNs);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
long DtiPipe::Send(ethernetPacket packet, int64 timeNs);
```

## Description

The function sends data using the specified pipe.

If transmitting packets at a rate that exceeds the output capacity of the pipe, the pipe becomes full. In such cases, the last packet that could be enqueued will return a value of `1`. To receive notification when the pipe is ready to accept more packets, provide a callback function when calling [DtiOpen](CAPLfunctionDtiOpen.md).

## Parameters

- **pipeHandle**: The handle to an open pipe.
- **packet**: The Ethernet packet to be transmitted.
- **timeNs**: The exact time at which the packet should be transmitted.

## Return Values

- **0**: Opened the pipe successfully.
- **-1**: Failed to open the pipe.
- **1**: The pipe is full. The packet was enqueued and does not need to be sent again.

## Example

```plaintext
void sendPacket()
{
  long result;

  pipe = DtiOpen(port, delegate (dword p, long r) {
    if (r == 0)
      r = DtiSend(pipe, packet, timeNs);
  });

  if (pipe == 0)
  {
    write("Failed to open the pipe!");
    return;
  }

  result = DtiSend(pipe, packet, timeNs);

  if (result == -1)
    write("Failed to send packet!");
  else if (result == 1)
    write("Packet is pending");
}
```
