[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPRoutingActivationResponseInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_RoutingActivationResponseInd

# _DoIP_RoutingActivationResponseInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long _DoIP_RoutingActivationResponseInd(byte isSecureConnection, dword testerLogAddr, dword senderLogAddr, dword responseCode, dword reserved, dword oem);
```

## Description

A response to the routing activation request was received in a tester implementation. It is possible to continue with the connection or deny it. The callback can also define special treatment for secure connections.

## Parameters

- **isSecureConnection**: True if the connection is "secure" i.e., uses TLS.
- **testerLogAddr**: Logical address of the target of the message i.e., the tester.
- **senderLogAddr**: Logical address of the DoIP entity which sent the response.
- **responseCode**: Routing activation response code.
- **reserved**: The value of the **reserved** field in the response message.
- **oem**: The value of the **OEM** field in the response, or 0, if field is not used.

## Return Values

- **-1**: Treat the response as "denied" and abort connection attempt with an error.
- **0**: Continue with the "normal" interpretation of the response code.
- **1**: Treat the response as "success" and continue without TLS.
- **2**: Treat the response as "success" and continue with TLS.
- **other**: Reserved for future use, currently treated as 0.

## Example

```plaintext
long _DoIP_RoutingActivationResponseInd(byte isSecureConnection, dword testerLogAddr, dword senderLogAddr, dword responseCode, dword reserved, dword oem)
{
  write("[%.3f] routing activation response indication with sender logical address '%i' received", timenow()/100000.0, senderLogAddr);
  return 0;
}
```

© Vector Informatik GmbH  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)