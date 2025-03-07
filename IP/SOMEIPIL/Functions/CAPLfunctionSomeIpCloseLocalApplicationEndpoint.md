[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpCloseLocalApplicationEndpoint.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpCloseLocalApplicationEndpoint**

# SomeIpCloseLocalApplicationEndpoint

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
LONG SomeIpCloseLocalApplicationEndpoint( dword aepHandle );
```

## Description

Closes an Application Endpoint that was previously opened with [SomeIpOpenLocalApplicationEndpoint](CAPLfunctionSomeIpOpenLocalApplicationEndpoint.md).

Services and the objects assigned to the services (Eventgroups, Events, Fields, and Methods) are removed when the Application Endpoint is closed. If the Application Endpoint has to be reopened, all objects must be created again.

## Parameters

- **aepHandle**: Handle of the Application Endpoint that should be closed (see [SomeIpOpenLocalApplicationEndpoint](CAPLfunctionSomeIpOpenLocalApplicationEndpoint.md))

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key 't'
{
  DWORD aep; // Application Endpoint handle

  // open an Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // ... do something here

  // close the Application Endpoint
  SomeIpCloseLocalApplicationEndpoint(aep);
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)