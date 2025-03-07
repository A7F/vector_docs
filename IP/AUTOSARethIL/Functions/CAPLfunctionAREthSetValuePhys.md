[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSetValuePhys.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthSetValuePhys**

# AREthSetValuePhys

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthSetValuePhys( dword objectHandle, char valuePath[], float value);
```

## Description

This function can be used to set a physical value in the object specified in the **objectHandle** parameter. All necessary information such as data type and conversion formula must be stored in the FIBEX database.

**Note:**

- If no conversion formula is specified in the FIBEX database or the conversion formula of type **identical** (Factor 1, no Offset) is specified, the function returns an error code. In this case, the value must be specified in raw format (see [AREthSetValueDWord](CAPLfunctionAREthSetValueDWord.md), for example).
- For large numerical values, conversion from real numbers to integers can result in deviations.

## Parameters

- **objectHandle**: Handle to a AUTOSAR Eth IL object, which must be completely described in the AUTOSAR database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

- **valuePath**: Path of the value to be set. For specification of complex paths, a corresponding syntax must be adhered to (see also [Syntax for Database-based Access Paths](CAPLfunctionAREthSyntaxDatabaseAccessPath.md)).

- **value**: New physical value

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters **Member_value1** and **Member_value2**, and a return parameter **Result**. For the return parameter **Result** a factor and offset is set in the database.

```plaintext
variables
{
  dword gPm; // provided method handle
}

void Initialize()
{
  dword aep; // application endpoint handle
  dword psi; // provided service instance handle

  // open application endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create service instance
  psi = AREthCreateProvidedServiceInstance(aep,11,1);

  // create method
  gPm = AREthAddMethod(psi,31,"OnMethodRequest");
}

void OnMethodRequest(dword methodHandle,dword messageHandle,dword messageResponseHandle)
{
  WORD val1; // value of input parameter 1
  WORD val2; // value of input parameter 2
  dword res; // value of return parameter

  // get value from request
  val1 = (WORD)AREthGetValueDword(messageHandle,"Member_value1");
  val2 = (WORD)AREthGetValueDword(messageHandle,"Member_value2");

  // calculate result
  res = val1 + val2;

  // set response value
  AREthSetValuePhys(messageResponseHandle,"Result",(val1 + val2));
}
```

**See Also**

- [AREthFillValues](CAPLfunctionAREthFillValues.md)
- [AREthGetDestinationAddress](CAPLfunctionAREthGetDestinationAddress.md)
- [AREthGetDestinationPort](CAPLfunctionAREthGetDestinationPort.md)
- [AREthGetInterfaceVersion](CAPLfunctionAREthGetInterfaceVersion.md)
- [AREthGetLength](CAPLfunctionAREthGetLength.md)
- [AREthGetMessageId](CAPLfunctionAREthGetMessageId.md)
- [AREthGetMessageType](CAPLfunctionAREthGetMessageType.md)
- [AREthGetProtocol](CAPLfunctionAREthGetProtocol.md)
- [AREthGetProtocolVersion](CAPLfunctionAREthGetProtocolVersion.md)
- [AREthGetRequestId](CAPLfunctionAREthGetRequestId.md)
- [AREthGetReturnCode](CAPLfunctionAREthGetReturnCode.md)
- [AREthGetSourceAddress](CAPLfunctionAREthGetSourceAddress.md)
- [AREthGetSourcePort](CAPLfunctionAREthGetSourcePort.md)
- [AREthGetValue](CAPLfunctionAREthGetValue.md)
- [AREthGetValueDWord](CAPLfunctionAREthGetValueDWord.md)
- [AREthGetValueFloat](CAPLfunctionAREthGetValueFloat.md)
- [AREthGetValueInt64](CAPLfunctionAREthGetValueInt64.md)
- [AREthGetValueLong](CAPLfunctionAREthGetValueLong.md)
- [AREthGetValuePhys](CAPLfunctionAREthGetValuePhys.md)
- [AREthGetValueQWord](CAPLfunctionAREthGetValueQWord.md)
- [AREthGetValueString](CAPLfunctionAREthGetValueString.md)
- [AREthSetRequestId](CAPLfunctionAREthSetRequestId.md)
- [AREthSetReturnCode](CAPLfunctionAREthSetReturnCode.md)
- [AREthSetValue](CAPLfunctionAREthSetValue.md)
- [AREthSetValueDWord](CAPLfunctionAREthSetValueDWord.md)
- [AREthSetValueFloat](CAPLfunctionAREthSetValueFloat.md)
- [AREthSetValueInt64](CAPLfunctionAREthSetValueInt64.md)
- [AREthSetValueLong](CAPLfunctionAREthSetValueLong.md)
- [AREthSetValuePhys](#aanchor11265)
- [AREthSetValueQWord](CAPLfunctionAREthSetValueQWord.md)
- [AREthSetValueString](CAPLfunctionAREthSetValueString.md)
- [Syntax for Database-based Access Paths](CAPLfunctionAREthSyntaxDatabaseAccessPath.md)
- [Syntax for Predefined Service Discovery (SD) Access Paths](CAPLfunctionAREthSyntaxPredefinedSDAccessPath.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)