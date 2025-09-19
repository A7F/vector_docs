[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpRemoveProvidedEventGroup.md)

## SomeIpRemoveProvidedEventGroup

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpRemoveProvidedEventGroup

### Valid for: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long SomeIpRemoveProvidedEventGroup( dword pevgHandle );
```

### Description

Removes an Event Group from a Provided Service Instance. The Event Group was previously added by [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md).

The Events and Fields assigned to the Event Group are not deleted when the Event Group is closed.

### Parameters

- **pevgHandle**: Handle of the Event Group (see [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md)).

### Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

### Example

```plaintext
on key 't'
{
  DWORD aep; // Application Endpoint handle
  DWORD psi; // provided service handle
  DWORD peg; // provided Eventgroup handle

  // open an Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create service
  psi = SomeIpCreateProvidedServiceInstance(aep,10,1);

  // create Eventgroup
  peg = SomeIpAddProvidedEventGroup(psi,1);

  // ... do something here

  // remove the Eventgroup
  SomeIpRemoveProvidedEventGroup(peg);

  // ... Application Endpoint and provided Service Instance can still be used here
}
```

[See Also](javascript:void(0);)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
