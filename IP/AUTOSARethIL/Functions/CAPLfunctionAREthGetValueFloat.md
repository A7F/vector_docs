[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthGetValueFloat.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthGetValueFloat

# AREthGetValueFloat

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
float AREthGetValueFloat( dword objectHandle, char valuePath[] );
```

## Description

This function can be used to read out a raw value from the object specified in the **objectHandle** parameter. The value is accessed in this case via symbolic access paths.

**Note:**

- A corresponding syntax must be adhered to for specifying the access paths. The access path results from the database description of the value to be read (see also [Syntax for Database-based Access Paths](CAPLfunctionAREthSyntaxDatabaseAccessPath.md)).
- The content of a Service Discovery message can also be read out with this function. Here, the value is accessed via a predefined access path (see also [Syntax for Predefined SD Access Paths](CAPLfunctionAREthSyntaxPredefinedSDAccessPath.md)).

## Parameters

- **objectHandle**: Handle to a AUTOSAR Eth IL object, which must be completely described in the FIBEX database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

- **valuePath**: Access path of the value to be read out.

## Return Values

- **Raw value**: In the event of an error, the function returns the value 0. The [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

See [AREthGetValueDWord](CAPLfunctionAREthGetValueDWord.md)

[See Also](javascript:void(0);)
