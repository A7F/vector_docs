[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthAddFieldToEventgroup.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthAddFieldToEventgroup**

# AREthAddFieldToEventgroup

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthAddFieldToEventgroup( dword pevgHandle, dword pfHandle );
```

## Description

This function assigns a Field which was created by [AREthAddField](CAPLfunctionAREthAddField.md) to an Event Group which was created by [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md).

The Field can be removed from the Event Group with [AREthRemoveFieldFromEventGroup](CAPLfunctionAREthRemoveProvidedEventGroup.md).

## Parameters

- **pevgHandle**: Handle of the Event Group that should be assigned to an Event (see [AREthAddProvidedEventGroup](CAPLfunctionAREthAddProvidedEventGroup.md)).
- **pfHandle**: Handle of the Field that should be assigned to the Event Group (see [AREthAddField](CAPLfunctionAREthAddField.md)).

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

In this example, it is assumed that the utilized field is contained in the FIBEX database that is assigned to the CANoe configuration. The field has the **Notification ID** 30, the **Getter ID** 31, and the **Setter ID** 32. The data type of the field is a standard data type (for example, UINT8).

```plaintext
variables
{
  dword gPfld_A; // provided field handle
}

void Initialize()
{
  CONST dword FieldNotificationID = 30;
  CONST dword FieldGetterID       = 31;
  CONST dword FieldSetterID       = 32;

  dword aep;   // Application Endpoint handle
  dword psi;   // provided service handle
  dword peg;   // provided Eventgroup handle

  // open Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
  psi = AREthCreateProvidedServiceInstance(aep,12,1);

  // create Eventgroup
  peg = AREthAddProvidedEventGroup(psi,300);

  // create field and add field to Eventgroup
  gPfld_A = AREthAddField(psi, FieldNotificationID, FieldGetterID, FieldSetterID);
  AREthAddFieldToEventgroup(peg,gPfld_A);
}

on key 'n'
{
  // set value of field content (field has a common data type so no value path is needed)
  AREthSetValueDWord(gPfld_A,"",100);

  // commit field content ... notification is sent
  AREthCommitField(gPfld_A);
}
```

[See Also](javascript:void(0);)
