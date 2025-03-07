[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthAddField.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthAddField**

# AREthAddField

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
dword AREthAddField( dword psiHandle, long notificationId, long getterId, long setterId );
```

## Description

This function adds a field to a Provided Service Instance that was created by [AREthCreateProvidedServiceInstance](CAPLfunctionAREthCreateProvidedServiceInstance.md).

Field contents can be set using the corresponding access functions ([AREthSetValue...](CAPLfunctionAREthSetValue.md)). These changes are only applied when the [AREthCommitField](CAPLfunctionAREthCommitField.md) is called.

A field can be removed again using the [AREthRemoveField](CAPLfunctionAREthRemoveField.md) function.

## Parameters

- **psiHandle**: Handle of the Provided Service Instance that was created with [AREthCreateConsumerServiceInstance](CAPLfunctionAREthCreateProvidedServiceInstance.md).
- **notificationId**: Identifier of the field notification. If the field does not support a notifier, the value -1 must be specified here.
- **getterId**: Identifier of the Field Getter method. If a consumer calls the getter method, the field content is returned by default. If this default behavior is to be changed, a method with the `getterId` must be created (see also [AREthAddMethod](CAPLfunctionAREthAddMethod.md) and [&lt;OnAREthMethodRequest&gt;](CAPLfunctionOnAREthMethodRequest.md)). If the field does not support a getter method, the value -1 must be specified here.
- **setterId**: Identifier of the Field Setter method. If a consumer calls the setter method, the field content is overwritten by default and the new field content is then sent via a response. If this default behavior is to be changed, a method with the `getterId` must be created (see also [AREthAddMethod](CAPLfunctionAREthAddMethod.md) and [&lt;OnAREthMethodRequest&gt;](CAPLfunctionOnAREthMethodRequest.md)). If the field does not support a setter method, the value -1 must be specified here.

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle of the created field

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