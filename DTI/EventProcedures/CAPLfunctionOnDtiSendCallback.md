# onDtiSendCallback

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void onDtiSendCallback(dword pipeHandle, long result);
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
void onDtiSendCallback(DtiPipe pipe, long result);
```

## Description

The function is called when a pipe that was previously full is now able to accept packets again.

## Parameters

- **pipeHandle**: Handle to the pipe that calls this function, thus signaling that it is ready to accept packets again.
- **result**: Indicates whether the pending package has been successfully transferred to the network interface hardware.

## Return Values

—

## Example

```plaintext
void onDtiSendCallback(dword p, long r)
{
  if (r == SUCCESS)
    write("Pipe is ready!");
}

void openPipeFunction()
{
  pipe = DtiOpen(port, onDtiSendCallback);
}

void openPipeWithDelegate()
{
  pipe = DtiOpen(port, delegate(dword p, long r)
  {
    if (r == SUCCESS)
      write("Pipe is ready!");
  });
}
```
