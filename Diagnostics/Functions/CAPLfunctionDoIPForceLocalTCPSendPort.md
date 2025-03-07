[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPForceLocalTCPSendPort.md)

**CAPL Functions** » **Diagnostics** » **DoIP_ForceLocalTCPSendPort**

# DoIP_ForceLocalTCPSendPort

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Note**

- This value can also be configured in the DoIP.INI file.
- [DoIP_ForceLocalUDPSendPort](CAPLfunctionDoIPForceLocalUDPSendPort.md)

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```
long DoIP_ForceLocalTCPSendPort(dword forcedPort);
```

## Description

Forces local TCP send port to a specific value. According to ISO13400, the local send port for outgoing TCP connections should be dynamically selected. This function allows forcing the local TCP send port to a specific value, typically to 13400 to indicate DoIP. Note that specifying a **well-known** or system port (1..1023) might not work on most systems.

## Parameters

- **forcedPort**

  - 0: use a dynamically assigned value (default)
  - 1..65535: send from this local TCP port
  - other: reserved

## Return Values

- **0**: success
- **-10**: invalid parameter
- **Others**: reserved

## Example

```plaintext
On preStart
{
  // Make sure that tester starts TCP connection from the standard port
  DoIP_ForceLocalTCPSendPort(13400);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)