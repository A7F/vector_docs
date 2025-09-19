[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthCommitField.md)

CAPL Functions » Ethernet » AUTOSAR Eth IL » AREthCommitField

# AREthCommitField

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthCommitField( dword pfHandle );
```

## Description

Applies changes that were performed on a field with the access functions [AREthSetValue…](CAPLfunctionAREthSetValue.md).

If the value of the field has been changed, the notification message of the field is sent. An actual value change must exist for this. If the same value previously contained in the field is set, a notification message is not sent.

## Parameters

- **pfHandle**: Handle of the field that was created by [AREthAddField](CAPLfunctionAREthAddField.md).

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
  AREthAddFieldToEventGroup(peg,gPfld_A);
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
