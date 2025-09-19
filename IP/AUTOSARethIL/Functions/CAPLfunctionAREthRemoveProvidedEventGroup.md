[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthRemoveProvidedEventGroup.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthRemoveProvidedEventGroup

# AREthRemoveProvidedEventGroup

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthRemoveProvidedEventGroup( dword pevgHandle );
```

## Description

Removes an Event Group from a Provided Service Instance. The Event Group was previously added by [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md).

The Events and Fields assigned to the Event Group are not deleted when the Event Group is closed.

## Parameters

- **pevgHandle**: Handle of the Event Group (see [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md)).

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key 't'
{
  dword aep; // Application Endpoint handle
  dword psi; // provided service handle
  dword peg; // provided Eventgroup handle

  // open an Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create service
  psi = AREthCreateProvidedServiceInstance(aep,10,1);

  // create Eventgroup
  peg = AREthAddProvidedEventGroup(psi,1);

  // ... do something here

  // remove the Eventgroup
  AREthRemoveProvidedEventGroup(peg);

  // ... Application Endpoint and provided Service Instance can still be used here
}
```

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
