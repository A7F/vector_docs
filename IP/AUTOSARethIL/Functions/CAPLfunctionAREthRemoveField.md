[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthRemoveField.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthRemoveField**

# AREthRemoveField

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthRemoveField( dword pfHandle );
```

## Description

This function removes a field from a Provided Service Instance.

The notification callback registered with [AREthAddField](CAPLfunctionAREthAddField.md) is no longer called after this function is called. The field notification is no longer sent by the AUTOSAR Eth IL, and the AUTOSAR Eth IL will no longer respond to Field Setter and Field Getter methods.

## Parameters

- **pfHandle**: Handle of the field that was created by [AREthAddField](CAPLfunctionAREthAddField.md).

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

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
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);
  // create Service Instance
  psi = AREthCreateProvidedServiceInstance(aep,12,1);
  // create Eventgroup
  peg = AREthAddProvidedEventGroup(psi,300);
  // create field and add field to Eventgroup
  gPfld_A = AREthAddField(psi, FieldNotificationID, FieldGetterID, FieldSetterID);
  AREthAddFieldToEventGroup(peg,gPfld_A);
}

on key 'r'
{
  AREthRemoveField (gPfld_A);
}
```

**See Also**: [AREthAddEvent](CAPLfunctionAREthAddEvent.md#aanchor12631), [AREthAddField](CAPLfunctionAREthAddField.md#aanchor27760), [AREthRemoveFieldFromEventgroup](CAPLfunctionAREthRemoveFieldFromEventgroup.md#aanchor28035)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
