# SomeIpAddField

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpAddField( dword psiHandle, long notificationId, long getterId, long setterId );
```

## Description

This function adds a field to a Provided Service Instance that was created by [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md).

Field contents can be set using the corresponding access functions ([SomeIpSetValue...](CAPLfunctionSomeIpSetValue.md)). These changes are only applied when the [SomeIpCommitField](CAPLfunctionSomeIpCommitField.md) is called.

A field can be removed again using the [SomeIpRemoveField](CAPLfunctionSomeIpRemoveField.md) function.

## Parameters

- **psiHandle**: Handle of the Provided Service Instance that was created with [SomeIpCreateConsumerServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md).
- **notificationId**: Identifier of the field notification. If the field does not support a notifier, the value -1 must be specified here.
- **getterId**: Identifier of the Field Getter method. If a consumer calls the getter method, the field content is returned by default. If this default behavior is to be changed, a method with the `getterId` must be created (see also [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md) and [&lt;OnSomeIpMethodRequest&gt;](CAPLfunctionOnSomeIpMethodRequest.md)). If the field does not support a getter method, the value -1 must be specified here.
- **setterId**: Identifier of the Field Setter method. If a consumer calls the setter method, the field content is overwritten by default and the new field content is then sent via a response. If this default behavior is to be changed, a method with the `getterId` must be created (see also [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md) and [&lt;OnSomeIpMethodRequest&gt;](CAPLfunctionOnSomeIpMethodRequest.md)). If the field does not support a setter method, the value -1 must be specified here.

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Handle of the created field

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
  SomeIpAddFieldToEventGroup(peg,gPfld_A);
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
