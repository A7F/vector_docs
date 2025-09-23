# SomeIpSetValueLong

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpSetValueLong( dword objectHandle, char valuePath[], long value );
```

## Description

This function can be used to set a raw value in the object specified in the **objectHandle** parameter. The value is accessed in this case via symbolic access paths.

**Note:**

- A corresponding syntax must be adhered to for specifying the access paths. The access path results from the database description of the value to be read (see also [Syntax for Database-based Access Paths](CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md)).
- The content of a Service Discovery message can also be read out with this function. Here, the value is accessed via a predefined access path (see also [Syntax for Predefined SD Access Paths](CAPLfunctionSomeIpSyntaxPredefinedSDAccessPath.md)).

## Parameters

- **objectHandle**: Handle to a SOME/IP IL object, which must be completely described in the FIBEX database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md).

- **valuePath**: Access path of the value to be set.

- **value**: Raw Value

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

See [SomeIpSetValueDWord](CAPLfunctionSomeIpSetValueDWord.md)

[See Also](javascript:void(0);)
