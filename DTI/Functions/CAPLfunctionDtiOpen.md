# DtiOpen

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword DtiOpen(ethernetPort port); // form 1`
- `dword DtiOpen(ethernetPort port, functionPointer onDtiSendCallback); // form 2`

## Method Syntax

- `DtiPipe DtiPipe::Open(ethernetPort port); // form 1`
- `DtiPipe DtiPipe::Open(ethernetPort port, functionPointer onDtiSendCallback); // form 2`

## Description

This function opens a pipe which allows the deterministic transfer of data.

Pipes can only be opened on simulation ports. If you provide a measurement port, the procedure fails.

Check the returned value to ensure that the pipe is valid. If you are using the method syntax, call [DtiIsValid](CAPLfunctionDtiIsValid.md) instead.

The [DTI API](../../../CANoeCANalyzer/Ethernet/DTI/DTIAPI.md) is supported by the VN5650 network interface.

## Parameters

- **port**: The measurement port on which the pipe will be opened.
- **onDtiSendCallback**: Pointer to a function that is called when a previously full pipe can accept packets again.

## Return Values

- **0**: The function failed. See the output of the Write window for more information.
- **Any other value**: A valid handle identifying the created pipe.

## Example

```c
void openPipe()
{
  dword pipe;
  long result;

  pipe = DtiOpen(port, delegate (dword p, long r){
    if (r == 0)
      r = DtiSend(pipe, packet, timeNs);
  });

  if (pipe == 0)
    write("Failed to open the pipe!");

  return pipe;
}
```
