[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpReleaseProvidedServiceInstance.md)

# SomeIpReleaseProvidedServiceInstance

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpReleaseProvidedServiceInstance

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpReleaseProvidedServiceInstance( dword psiHandle );
```

## Description

Deletes a Provided Service Instance that was created by [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md).

All objects (Eventgroups, Events, Fields, and Methods) are also closed when the Service Instance is closed. If the Service Instance is newly created, all objects must also be newly created.

## Parameters

- **psiHandle**: Handle of the Provided Service Instance to be deleted (see [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md)).

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key 't'
{
  DWORD aep; // Application Endpoint handle
  DWORD psi; // provided service handle

  // open an Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create service
  psi = SomeIpCreateProvidedServiceInstance(aep,10,1);

  // ... do something here

  // close the provided Service Instance
  SomeIpReleaseProvidedServiceInstance(psi);

  // ... Application Endpoint can still be used here
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
