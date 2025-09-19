# DoIP_SetRoutingActivationType

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long DoIP_SetRoutingActivationType(char ecuQualifier[], dword activationType);
long DoIP_SetRoutingActivationType(dword activationType);
```

## Description

Configures the value of the ISO 13400-2 parameter **routing activation request activation type** sent by the tester the next time it starts to communicate with a vehicle on the built-in channel. If no ECU qualifier is given, the channel selected with [DiagSetTarget](CAPLfunctionDiagSetTarget.md) is used.

## Parameters

- **ecuQualifier**: Set the activation type on the channel to the given target.
- **activationType**: Send this activation type value, e.g. **0** for default, 0xE1-0xFF for OEM-specific.

## Return Values

[Error Code](../../../CANoeCANalyzer/Windows/Write/WriteWindowNotifications/17Diagnostics.md)

## Example

- These functions only work if the tester program uses the built-in DoIP channels!
- For configuration and handling of the activation type in a vehicle simulation, please refer to these (callback) functions from the DoIP.DLL:
  - [_DoIP_RoutingActivationRequest](CAPLfunctionDoIPRoutingActivationRequest.md)
  - [DoIP_ConfigureRoutingActivationResponse](CAPLfunctionDoIPConfigureRoutingActivationResponse.md)

```c
// Try to connect to vehicle, changing activation type on failure
testcase TryRoutingType()
{
  diagRequest ECU.DefaultSession_Start req;
  long status;

  // Try the default routing activation type first
  DoIP_SetRoutingActivationType("ECU", 0);

  req.SendRequest();
  status = testWaitForDiagRequestSent(req, 2900);
  switch(status)
  {
    case 1:
      TestStepPass("Connect worked with default activation type");
      return;
    case 0:
      TestStepFail("Timeout trying to connect! No vehicle?");
      return;
    case -92:
      TestStep("", "Error on TP level, probably wrong activation type?");
      break;
    default:
      TestStepWarning("", "Connecting with default activation type returned %d", status);
  }

  // Try again with arbitrary "OEM-specific" activation type
  DoIP_SetRoutingActivationType("ECU", 0xF0);

  req.SendRequest();
  status = testWaitForDiagRequestSent(req, 2900);
  if (status == 1)
    TestStepPass("Successfully connected with OEM-specific activation type");
  else if(status == 0)
    TestStepFail("Timeout trying to connect!");
  else
    TestStepFail("", "Connecting with OEM-specific activation type returned %d", status);
}
```

[_DoIP_RoutingActivationRequest](CAPLfunctionDoIPRoutingActivationRequest.md) • [DoIP_ConfigureRoutingActivationResponse](CAPLfunctionDoIPConfigureRoutingActivationResponse.md)
