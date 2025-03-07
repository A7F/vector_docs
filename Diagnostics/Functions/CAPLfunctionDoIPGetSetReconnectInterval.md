[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPGetSetReconnectInterval.md)

**CAPL Functions** » **Diagnostics** » **DoIP_GetReconnectInterval, DoIP_SetReconnectInterval**

# DoIP_GetReconnectInterval, DoIP_SetReconnectInterval

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
dword DoIP_GetReconnectInterval(); // form 1
void DoIP_SetReconnectInterval(dword reconnectInterval_ms, dword maxAttempts); // form 2
```

## Description

Get the distance between reconnect attempts by the tester, or configure the way the tester repeats reconnect attempts to the vehicle.

When the vehicle closes the connection the tester will wait for a time configured with [DoIP_SetReconnectDelay](CAPLfunctionDoIPGetSetReconnectDelay.md) before trying to connect to the vehicle again. It will then send up to **maxAttempts** TCP connection requests to the ECU, waiting **reconnectInterval_ms** between attempts.

## Parameters

- **reconnectInterval_ms**  
  >0  
  After sending a TCP connection request the tester will wait this long for the vehicle to accept it. If it does not respond, the tester will send another request, unless the maximum number of attempts is reached.

- **maxAttempts**  
  Maximum number of reconnection attempts the tester will perform.

## Return Values

- **Form 1**  
  dword reconnectInterval_ms

- **Form 2**  
  void

## Example

This value can also be configured in the DoIP.INI file.

```plaintext
void Configure_DoIP()
{
  //...
  // Configure up to 15 attempts every 200 ms ...
  DoIP_SetReconnectInterval(200, 15);

  // ... starting 500 ms after the vehicle closes the connection
  DoIP_SetReconnectDelay(500);

  // Note that it may take over 500 ms + 15 * 200 ms = 3500 ms for the tester to
  // detect that the vehicle is no longer present!
  // Wait functions must take this into account.
}
```

[DoIP_GetReconnectDelay](CAPLfunctionDoIPGetSetReconnectDelay.md) • [DoIP_SetReconnectDelay](CAPLfunctionDoIPGetSetReconnectDelay.md)

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)