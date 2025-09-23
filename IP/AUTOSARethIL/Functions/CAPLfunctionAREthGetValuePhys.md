# AREthGetValuePhys

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
float AREthGetValuePhys( dword objectHandle, char valuePath[] );
```

## Description

This function can be used to read out a physical value from the object specified in the **objectHandle** parameter. All necessary information such as data type and conversion formula must be stored in the FIBEX database.

**Note:**

- If no conversion formula is stored in the database, **identical** (Factor 1, no Offset) is applied implicitly.
- For large numerical values, conversion from real numbers to integers can result in deviations.

## Parameters

- **objectHandle**: Handle to a AUTOSAR Eth IL Object. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

- **valuePath**: Path of the value to be read out. For specification of complex paths, a corresponding syntax must be adhered to (see also [Syntax for Database-based Access Paths](CAPLfunctionAREthSyntaxDatabaseAccessPath.md)).

## Return Values

- **Physical value**: In the event of an error, the function returns the value 0. The [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function can then be used to check whether the value is valid or an error has occurred.

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters **Member_value1** and **Member_value2**, and a return parameter **Result**. For the variables **Member_value1** and **Member_value2** a factor and offset is set in the database.

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
  val1 = (WORD)AREthGetValuePhys(messageHandle,"Member_value1");
  val2 = (WORD)AREthGetValuePhys(messageHandle,"Member_value2");

  // calculate result
  res = val1 + val2;

  // set response value
  AREthSetValueDWord(messageResponseHandle,"Result",(val1 + val2));
}
```

[See Also](javascript:void(0);)
