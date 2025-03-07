[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPEnableTLS.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_EnableTLS

# DoIP_EnableTLS

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

TLS can be used only for simulation nodes (CAPL node, test module, etc.) that have security enabled for the TCP/IP stack, configured for the node with DoIP.dll in the CANoe Security Configuration.

## Function Syntax

```plaintext
void DoIP_EnableTLS(dword mode, char name[]);
```

## Description

Enables secure communication for DoIP tester or ECU simulation. If enabled, DoIP communication is carried out via TLS (Transport Layer Security).

**Note**  
TLS must be enabled before DoIP communication starts. It is recommended to call the function **on preStart** or **on start** before configuring TP parameters.

## Parameters

- **mode**  
  - 0: disable TLS, no secure communication.
  - 1: enable TLS by routing activation response code (RARC) 0x07.
  - 2: (tester only) enable TLS. Only secure connection is allowed. If ECU responds with RARC 0x10 on the first unsecure routing activation, the tester stops communication.
  - 3: (tester only) enable TLS. Tester connects to ECU directly via TLS without establishing connection on unsecure port (e.g. 13400).

- **name**  
  - (ECU simulation) name of the server certificate, which must be used for TLS connection. It must be one of the certificates, available in the security profile, selected for the TCP/IP stack of the ECU simulation node.
  - (Tester) name of the client certificate. Currently, client certificates are not supported for DoIP. The parameter is reserved for future use. It must be an empty string "".

## Return Values

—

## Example

**Example 1**

```plaintext
on preStart
{
  // enable TLS for ECU simulation
  // use certificate 'Server1' (security profile 'DoIP over TLS Demo')
  DoIP_EnableTLS(1, "Server1");
}
```

**Example 2**

```plaintext
on preStart
{
  // enable TLS for tester
  DoIP_EnableTLS(2, "");
}
```

[_Diag_DataRequest](CAPLfunctionDiagDataRequest.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)