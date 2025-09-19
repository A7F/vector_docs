[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthReleaseProvidedServiceInstance.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthReleaseProvidedServiceInstance

# AREthReleaseProvidedServiceInstance

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthReleaseProvidedServiceInstance( dword psiHandle );
```

## Description

Deletes a Provided Service Instance that was created by [AREthCreateProvidedServiceInstance](CAPLfunctionAREthCreateProvidedServiceInstance.md).

All objects (Eventgroups, Events, Fields, and Methods) are also closed when the Service Instance is closed. If the Service Instance is newly created, all objects must also be newly created.

## Parameters

- **psiHandle**: Handle of the Provided Service Instance to be deleted (see [AREthCreateProvidedServiceInstance](CAPLfunctionAREthCreateProvidedServiceInstance.md)).

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key 't'
{
  dword aep; // Application Endpoint handle
  dword psi; // provided service handle

  // open an Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create service
  psi = AREthCreateProvidedServiceInstance(aep,10,1);

  // ... do something here

  // close the provided Service Instance
  AREthReleaseProvidedServiceInstance(psi);

  // ... Application Endpoint can still be used here
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
