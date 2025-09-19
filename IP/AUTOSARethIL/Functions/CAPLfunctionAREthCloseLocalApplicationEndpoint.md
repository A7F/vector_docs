[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthCloseLocalApplicationEndpoint.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthCloseLocalApplicationEndpoint

# AREthCloseLocalApplicationEndpoint

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
LONG AREthCloseLocalApplicationEndpoint( dword aepHandle );
```

## Description

Closes an Application Endpoint that was previously opened with [AREthOpenLocalApplicationEndpoint](CAPLfunctionAREthOpenLocalApplicationEndpoint.md).

Services and the objects assigned to the services (Eventgroups, Events, Fields, and Methods) are removed when the Application Endpoint is closed. If the Application Endpoint has to be reopened, all objects must be created again.

## Parameters

- **aepHandle**: Handle of the Application Endpoint that should be closed (see [AREthOpenLocalApplicationEndpoint](CAPLfunctionAREthOpenLocalApplicationEndpoint.md))

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key 't'
{
  dword aep; // Application Endpoint handle

  // open an Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // ... do something here

  // close the Application Endpoint
  AREthCloseLocalApplicationEndpoint(aep);
}
```

See Also: [AREthCloseLocalApplicationEndpoint](#aanchor3596), [AREthOpenLocalApplicationEndpoint](CAPLfunctionAREthOpenLocalApplicationEndpoint.md#aanchor9093), [AREthTlsAuthenticateAsClientWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsClientWithConfiguration.md#aanchor31467), [AREthTlsAuthenticateAsServerWithConfiguration](CAPLFunctionAREthTlsAuthenticateAsServerWithConfiguration.md#aanchor23311)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
