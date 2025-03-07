[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DTI/EventProcedures/CAPLfunctionOnDtiSendCallback.md)

**CAPL Functions** » [DTI](../CAPLfunctionsDTIOverview.md) » onDtiSendCallback

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)