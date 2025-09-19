[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpRemoveField.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpRemoveField

# SomeIpRemoveField

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpRemoveField( DWORD pfHandle );
```

## Description

This function removes a field from a Provided Service Instance.

The notification callback registered with [SomeIpAddField](CAPLfunctionSomeIpAddField.md) is no longer called after this function is called. The field notification is no longer sent by the SOME/IP IL, and the SOME/IP IL will no longer respond to Field Setter and Field Getter methods.

## Parameters

- **pfHandle**: Handle of the field that was created by [SomeIpAddField](CAPLfunctionSomeIpAddField.md).

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
variables
{
  DWORD gPfld_A; // provided field handle
}

on start()
{
  CONST DWORD FieldNotificationID = 30;
  CONST DWORD FieldGetterID = 31;
  CONST DWORD FieldSetterID = 32;

  DWORD aep; // Application Endpoint handle
  DWORD psi; // provided service handle
  DWORD peg; // provided Eventgroup handle

  // open Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  psi = SomeIpCreateProvidedServiceInstance(aep,12,1);
  // create Eventgroup
  peg = SomeIpAddProvidedEventGroup(psi,300);
  // create field and add field to Eventgroup
  gPfld_A = SomeIpAddField(psi, FieldNotificationID, FieldGetterID, FieldSetterID);
  SomeIpAddFieldToEventGroup(peg,gPfld_A);
}

on key 'r'
{
  SomeIpRemoveField(gPfld_A);
}
```

[See Also](javascript:void(0);)
