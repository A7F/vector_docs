[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPSetLocalIPaddressVersion.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_SetLocalIPaddressVersion

# DoIP_SetLocalIPaddressVersion

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_SetLocalIPaddressVersion(dword addressIPVersion);
```

## Description

When no local IP address is given explicitly, select the local address according to the priority set with this function. For example, this will allow the selection of a specific address type when only the network adapter is configured.

## Parameters

- **addressIPVersion**
  - 0: Use IPv6 address if no IPv4 address is available (default)
  - 4: Use only IPv4 address
  - 6: Use only IPv6 address other: reserved

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

```plaintext
// Use the IPv6 address configured for the selected network adapter
char buffer[256];
DiagGetCommParameter( "DoIP.TESTER_Adapter", 0, buffer, elcount( buffer));
DoIP_SetTesterAdapter( buffer);
DoIP_SetLocalIPaddressVersion( 6);
```

[DoIP_SetLocalIPaddress](CAPLfunctionDoIPSetLocalIPaddress.md) • [DoIP_SetTesterAdapter](CAPLfunctionDoIPSetTesterAdapter.md) • [DoIP_SetVehicleAdapter](CAPLfunctionDoIPSetVehicleAdapter.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)