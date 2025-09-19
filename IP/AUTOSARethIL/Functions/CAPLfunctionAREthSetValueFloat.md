[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSetValueFloat.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthSetValueFloat**

# AREthSetValueFloat

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthSetValueFloat( dword objectHandle, char valuePath[], float value );
```

## Description

This function can be used to set a raw value in the object specified in the **objectHandle** parameter. The value is accessed in this case via symbolic access paths.

**Note**

- A corresponding syntax must be adhered to for specifying the access paths. The access path results from the database description of the value to be read (see also [Syntax for Database-based Access Paths](CAPLfunctionAREthSyntaxDatabaseAccessPath.md)).
- The content of a Service Discovery message can also be read out with this function. Here, the value is accessed via a predefined access path (see also [Syntax for Predefined SD Access Paths](CAPLfunctionAREthSyntaxPredefinedSDAccessPath.md)).

## Parameters

- **objectHandle**: Handle to a AUTOSAR Eth IL object, which must be completely described in the AUTOSAR database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

- **valuePath**: Access path of the value to be set.

- **value**: Raw Value

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

See [AREthSetValueDWord](CAPLfunctionAREthSetValueDWord.md)

[See Also](javascript:void(0);)
