[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalUnregisterApplicationProtocol.md)

## SecurityLocalUnregisterApplicationProtocol

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalUnregisterApplicationProtocol

**Valid for:** CANoe DE • CANoe4SW DE

### Function Syntax

- `long SecurityLocalUnregisterApplicationProtocol(char applicationProtocolUserDefinedId[]) // form 1`
- `long SecurityLocalUnregisterApplicationProtocol(char applicationProtocolUserDefinedId[], dword vLanId) // form 2`

### Description

Unregisters the reception of the application protocol with the specified User Defined Id. The node will no longer receive this application protocol and the callbacks [OnSecurityLocalApplicationProtocolRxFinished](../CallbackHandler/CAPLfunctionOnSecurityLocalApplicationProtocolRxFinished.md) or [OnSecurityLocalApplicationProtocolTxFinished](../CallbackHandler/CAPLfunctionOnSecurityLocalApplicationProtocolTxFinished.md) will also no longer be called. The call of [SecurityLocalAllowNetworkWideRegistrations](CAPLfunctionSecurityLocalAllowNetworkWideRegistrations.md) is a precondition for using this function.

### Parameters

—

### Return Values

- **1**: Success.
- **-1**: The specified applicationProtocolUserDefinedId has not been registered.
- **-2**: `SecurityLocalAllowNetworkWideRegistrations` must be called before using this function.
- **-5**: The specified applicationProtocolUserDefinedId has not been registered on the same VLAN.
- **-6**: The Security Manager does not support this function. (Security Manager V2.3.9 or later required).
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

### Example

```c
// Implement this in an Observer-Node to receive callbacks of Application-Protocol for real ECUs
on preStart
{
  long result = 0;
  result = SecurityLocalAllowNetworkWideRegistrations();
  Write("The call of SecurityLocalAllowNetworkWideRegistrations returned %i", result);
}

on start
{
  dword result = 0;
  result = SecurityLocalRegisterApplicationProtocol("APPLICATIONPROTOCOLNAME",10);
  Write("SecurityLocalRegisterApplicationProtocol to register to APPLICATIONPROTOCOLNAME on VLAN 10 returned %i", result);
}

void OnLocalSecurityApplicationProtocolRxFinished(char applicationProtocolName[], byte payload[], dword payloadLength, dword result)
{
  if(strncmp(applicationProtocolName,"APPLICATIONPROTOCOLNAME",23) == 0)
  {
    write("Received Application Protocol %s", applicationProtocolName);
  }
}

on stopMeasurement
{
  dword result = 0;
  result = SecurityLocalUnregisterApplicationProtocol("APPLICATIONPROTOCOLNAME",10);
  Write("SecurityLocalUnregisterApplicationProtocol to unregister from APPLICATIONPROTOCOLNAME on VLAN 10 returned %i", result);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
