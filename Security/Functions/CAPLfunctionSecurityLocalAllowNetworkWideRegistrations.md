[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalAllowNetworkWideRegistrations.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalAllowNetworkWideRegistrations

# SecurityLocalAllowNetworkWideRegistrations

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long SecurityLocalAllowNetworkWideRegistrations()` // form 1
- `long SecurityLocalAllowNetworkWideRegistrations(char databaseNetwork)` // form 2
- `long SecurityLocalAllowNetworkWideRegistrations(char databaseNetwork, dword vLanId)` // form 3

## Description

Allows to register and unregister to network related security data. It is a precondition for using [SecurityLocalRegisterApplicationProtocol](CAPLfunctionSecurityLocalRegisterApplicationProtocol.md) and [SecurityLocalUnregisterApplicationProtocol](CAPLfunctionSecurityLocalUnregisterApplicationProtocol.md).

For use with a simulation node, the function has to be called in the **on prestart** event of the simulation node which is not defined in the database. The function can’t be executed after measurement has started. The function can’t be executed by database nodes.

For use with a test module, the function can be called at any time.

If the parameter DatabaseNetwork is specified, only network with this in the assigned database is considered when registering application protocols.

A node can call this function only once. A secondary call is ignored and returns -2.

## Parameters

- **databaseName**: The name of the network in the database which shall be considered, when registering application protocols. If this parameter is not specified, all networks in the database are considered.
- **vLanId**: The vLan Id number identifies the Ethernet vLAN. Only PDUs which are transmitted on this vLAN shall be considered, when registering application protocols. If this parameter is not specified, all vLANs are considered.

## Return Values

- **1**: Success
- **-2**: Function call is ignored, because it has already been called before.
- **-7**: This function can only be used at Non-Database Nodes.
- **-10**: Security is not usable. Reasons can be: Security Manager version is too old. Tool Version is too old. Security Profile is invalid.

## Example

```plaintext
//Implement this in an Observer-Node to receive callbacks of Application-Protocol for real ECUs
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

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
