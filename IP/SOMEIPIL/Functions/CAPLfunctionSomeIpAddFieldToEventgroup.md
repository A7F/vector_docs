[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpAddFieldToEventgroup.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpAddFieldToEventgroup

# SomeIpAddFieldToEventgroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpAddFieldToEventgroup( dword pevgHandle, dword pfHandle );
```

## Description

This function assigns a Field which was created by [SomeIpAddField](CAPLfunctionSomeIpAddField.md) to an Event Group which was created by [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md).

The Field can be removed from the Event Group with [SomeIpRemoveFieldFromEventGroup](CAPLfunctionSomeIpRemoveProvidedEventGroup.md).

## Parameters

- **pevgHandle**: Handle of the Event Group that should be assigned to an Event (see [SomeIpAddProvidedEventGroup](CAPLfunctionSomeIpAddProvidedEventGroup.md)).
- **pfHandle**: Handle of the Field that should be assigned to the Event Group (see [SomeIpAddField](CAPLfunctionSomeIpAddField.md)).

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

In this example, it is assumed that the utilized field is contained in the FIBEX database that is assigned to the CANoe configuration. The field has the **Notification ID** 30, the **Getter ID** 31, and the **Setter ID** 32. The data type of the field is a standard data type (for example, UINT8).

```plaintext
variables
{
  DWORD gPfld_A; // provided field handle
}

void Initialize()
{
  CONST DWORD FieldNotificationID = 30;
  CONST DWORD FieldGetterID       = 31;
  CONST DWORD FieldSetterID       = 32;

  DWORD aep;   // Application Endpoint handle
  DWORD psi;   // provided service handle
  DWORD peg;   // provided Eventgroup handle

  // open Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  psi = SomeIpCreateProvidedServiceInstance(aep,12,1);

  // create Eventgroup
  peg = SomeIpAddProvidedEventGroup(psi,300);

  // create field and add field to Eventgroup
  gPfld_A = SomeIpAddField(psi, FieldNotificationID, FieldGetterID, FieldSetterID);
  SomeIpAddFieldToEventgroup(peg,gPfld_A);
}

on key 'n'
{
  // set value of field content (field has a common data type so no value path is needed)
  SomeIpSetValueDWord(gPfld_A,"",100);

  // commit field content ... notification is sent
  SomeIpCommitField(gPfld_A);
}
```

[See Also](javascript:void(0);)