# SomeIpRemoveValue

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpRemoveValue( dword objectHandle, char valuePath[]);
```

## Description

This function can be used to remove a value in the object specified in the **objectHandle** parameter. The value is removed in this case via symbolic access paths.

The function may be used on entries of dynamic arrays or optional values which shall be removed. In the case of arrays successive entries are moved forward.

**Note**

- A corresponding syntax must be adhered to for specifying the access paths. The access path results from the database description of the value to be read (see also [Syntax for Database-based Access Paths](CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md)).
- The content of a Service Discovery message can also be modified with this function. Here, the value is accessed via a predefined access path (see also [Syntax for Predefined SD Access Paths](CAPLfunctionSomeIpSyntaxPredefinedSDAccessPath.md)).

## Parameters

- **objectHandle**: Handle to a SOME/IP IL object, which must be completely described in the FIBEX database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md).

- **valuePath**: Access path of the value to be read out.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)

- [AREthRemoveValue](../../AUTOSARethIL/Functions/CAPLfunctionAREthRemoveValue.md#aanchor13236)
- [SomeIpFillValues](CAPLfunctionSomeIpFillValues.md#aanchor9390)
- [SomeIpGetDestinationAddress](CAPLfunctionSomeIpGetDestinationAddress.md#aanchor13351)
- [SomeIpGetDestinationPort](CAPLfunctionSomeIpGetDestinationPort.md#aanchor3855)
- [SomeIpGetInterfaceVersion](CAPLfunctionSomeIpGetInterfaceVersion.md#aanchor25213)
- [SomeIpGetLength](CAPLfunctionSomeIpGetLength.md#aanchor470)
- [SomeIpGetMessageId](CAPLfunctionSomeIpGetMessageId.md#aanchor25989)
- [SomeIpGetMessageType](CAPLfunctionSomeIpGetMessageType.md#aanchor5989)
- [SomeIpGetProtocol](CAPLfunctionSomeIpGetProtocol.md#aanchor30044)
- [SomeIpGetProtocolVersion](CAPLfunctionSomeIpGetProtocolVersion.md#aanchor29343)
- [SomeIpGetRequestId](CAPLfunctionSomeIpGetRequestId.md#aanchor2711)
- [SomeIpGetReturnCode](CAPLfunctionSomeIpGetReturnCode.md#aanchor62)
- [SomeIpGetSourceAddress](CAPLfunctionSomeIpGetSourceAddress.md#aanchor4073)
- [SomeIpGetSourcePort](CAPLfunctionSomeIpGetSourcePort.md#aanchor4748)
- [SomeIpGetValue...](CAPLfunctionSomeIpGetValue.md#aanchor1803)
- [SomeIpGetValueDWord](CAPLfunctionSomeIpGetValueDWord.md#aanchor29598)
- [SomeIpGetValueFloat](CAPLfunctionSomeIpGetValueFloat.md#aanchor3783)
- [SomeIpGetValueInt64](CAPLfunctionSomeIpGetValueInt64.md#aanchor17844)
- [SomeIpGetValueLong](CAPLfunctionSomeIpGetValueLong.md#aanchor30178)
- [SomeIpGetValuePhys](CAPLfunctionSomeIpGetValuePhys.md#aanchor6883)
- [SomeIpGetValueQWord](CAPLfunctionSomeIpGetValueQWord.md#aanchor25078)
- [SomeIpGetValueString](CAPLfunctionSomeIpGetValueString.md#aanchor8540)
- [SomeIpRemoveValue](#aanchor11749)
- [SomeIpSetRequestId](CAPLfunctionSomeIpSetRequestId.md#aanchor22159)
- [SomeIpSetReturnCode](CAPLfunctionSomeIpSetReturnCode.md#aanchor5016)
- [SomeIpSetValue...](CAPLfunctionSomeIpSetValue.md#aanchor1574)
- [SomeIpSetValueDWord](CAPLfunctionSomeIpSetValueDWord.md#aanchor25522)
- [SomeIpSetValueFloat](CAPLfunctionSomeIpSetValueFloat.md#aanchor27752)
- [SomeIpSetValueInt64](CAPLfunctionSomeIpSetValueInt64.md#aanchor6475)
- [SomeIpSetValueLong](CAPLfunctionSomeIpSetValueLong.md#aanchor21822)
- [SomeIpSetValuePhys](CAPLfunctionSomeIpSetValuePhys.md#aanchor23183)
- [SomeIpSetValueQWord](CAPLfunctionSomeIpSetValueQWord.md#aanchor20159)
- [SomeIpSetValueString](CAPLfunctionSomeIpSetValueString.md#aanchor19079)
- [Syntax for Database-based Access Paths](CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md#aanchor16667)
- [Syntax for Predefined Service Discovery (SD) Access Paths](CAPLfunctionSomeIpSyntaxPredefinedSDAccessPath.md#aanchor26107)
