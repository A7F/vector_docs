# AREthRemoveMethodCall

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
LONG AREthRemoveMethodCall( dword methodHandle );
```

## Description

Removes a method call of the Consumed Service Instance. The method was previously added by [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

Afterwards the method handle is no longer valid and cannot be used anymore with [AREthCallMethod](CAPLfunctionAREthCallMethod.md).

## Parameters

- **methodHandle**: Handle of the method.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters **Member_value1** and **Member_value2**, and a return parameter **Result**.

```plaintext
variables
{
  dword gMc; // global method call handle
}

on key 'e'
{
  dword csi; // consumed Service Instance handle
  dword mc;  // method call

  // open Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(0x11, 50002);
  csi = AREthCreateConsumedServiceInstance(aep,11,1);

  // create method call
  gMc = AREthCreateMethodCall(csi,31,"OnMethodResponse");

  // set the two input parameters of the method and call the method
  AREthSetValueDWord(gMc,"Member_value1",11);
  AREthSetValueDWord(gMc,"Member_value2",22);
  AREthCallMethod(gMc);
}

on key 'r'
{
  // remove method call
  AREthRemoveMethodCall(gMc);
}

void OnMethodResponse(dword methodCallHandle, dword messageResponseHandle )
{
  dword res; // value of return parameter

  // get the returned parameter values
  res = AREthGetValueDWord(messageResponseHandle,"Result");

  write("The method call returned value: %d",res);
}
```

[See Also](javascript:void(0);)
