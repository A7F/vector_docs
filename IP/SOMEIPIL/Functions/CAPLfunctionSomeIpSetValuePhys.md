[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpSetValuePhys.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpSetValuePhys**

# SomeIpSetValuePhys

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpSetValuePhys( dword objectHandle, char valuePath[], float value);
```

## Description

This function can be used to set a physical value in the object specified in the **objectHandle** parameter. All necessary information such as data type and conversion formula must be stored in the FIBEX database.

**Note:**

- If no conversion formula is stored in the database, **identical** (Factor 1, no Offset) is applied implicitly.
- For large numerical values, conversion from real numbers to integers can result in deviations.

## Parameters

- **objectHandle**: Handle to a SOME/IP IL Object. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md).

- **valuePath**: Path of the value to be set. For specification of complex paths, a corresponding syntax must be adhered to (see also [Syntax for Database-based Access Paths](CAPLfunctionSomeIpSyntaxDatabaseAccessPath.md)).

- **value**: New physical value

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters **Member_value1** and **Member_value2**, and a return parameter **Result**. For the return parameter **Result** a factor and offset is set in the database.

```plaintext
variables
{
  DWORD gPm; // provided method handle
}

void Initialize()
{
  DWORD aep; // application endpoint handle
  DWORD psi; // provided service instance handle

  // open application endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create service instance
  psi = SomeIpCreateProvidedServiceInstance(aep,11,1);

  // create method
  gPm = SomeIpAddMethod(psi,31,"OnMethodRequest");
}

void OnMethodRequest(dword methodHandle,dword messageHandle,dword messageResponseHandle)
{
  WORD val1; // value of input parameter 1
  WORD val2; // value of input parameter 2
  DWORD res; // value of return parameter

  // get value from request
  val1 = (WORD)SomeIpGetValueDword(messageHandle,"Member_value1");
  val2 = (WORD)SomeIpGetValueDword(messageHandle,"Member_value2");

  // calculate result
  res = val1 + val2;

  // set response value
  SomeIpSetValuePhys(messageResponseHandle,"Result",(val1 + val2));
}
```

[See Also](javascript:void(0);)