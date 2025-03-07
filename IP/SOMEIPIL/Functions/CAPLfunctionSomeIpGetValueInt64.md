[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetValueInt64.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpGetValueInt64**

# SomeIpGetValueInt64

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
int64 SomeIpGetValueInt64( dword objectHandle, char valuePath[] );
```

## Description

This function can be used to read out a raw value from the object specified in the **objectHandle** parameter. The value is accessed in this case via symbolic access paths.

**Note:**

- A corresponding syntax must be adhered to for specifying the access paths. The access path results from the database description of the value to be read (see also [Syntax for Database-based Access Paths](CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md)).
- The content of a Service Discovery message can also be read out with this function. Here, the value is accessed via a predefined access path (see also [Syntax for Predefined SD Access Paths](CAPLfunctionSomeIpSyntaxPredefinedSDAccessPath.md)).

## Parameters

- **objectHandle**: Handle to a SOME/IP IL object, which must be completely described in the FIBEX database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md).

- **valuePath**: Access path of the value to be read out.

## Return Values

- **Raw value**: In the event of an error, the function returns the value 0. The [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

See [SomeIpGetValueDWord](CAPLfunctionSomeIpGetValueDWord.md)

**See Also**

- [SomeIpGetValueDWord](CAPLfunctionSomeIpGetValueDWord.md)
- [SomeIpGetValueFloat](CAPLfunctionSomeIpGetValueFloat.md)
- [SomeIpGetValueInt64](#aanchor17844)
- [SomeIpGetValueLong](CAPLfunctionSomeIpGetValueLong.md)
- [SomeIpGetValuePhys](CAPLfunctionSomeIpGetValuePhys.md)
- [SomeIpGetValueQWord](CAPLfunctionSomeIpGetValueQWord.md)
- [SomeIpGetValueString](CAPLfunctionSomeIpGetValueString.md)
- [SomeIpRemoveValue](CAPLfunctionSomeIpRemoveValue.md)
- [SomeIpSetRequestId](CAPLfunctionSomeIpSetRequestId.md)
- [SomeIpSetReturnCode](CAPLfunctionSomeIpSetReturnCode.md)
- [SomeIpSetValueDWord](CAPLfunctionSomeIpSetValueDWord.md)
- [SomeIpSetValueFloat](CAPLfunctionSomeIpSetValueFloat.md)
- [SomeIpSetValueInt64](CAPLfunctionSomeIpSetValueInt64.md)
- [SomeIpSetValueLong](CAPLfunctionSomeIpSetValueLong.md)
- [SomeIpSetValuePhys](CAPLfunctionSomeIpSetValuePhys.md)
- [SomeIpSetValueQWord](CAPLfunctionSomeIpSetValueQWord.md)
- [SomeIpSetValueString](CAPLfunctionSomeIpSetValueString.md)
- [Syntax for Database-based Access Paths](CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md)
- [Syntax for Predefined Service Discovery (SD) Access Paths](CAPLfunctionSomeIpSyntaxPredefinedSDAccessPath.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)