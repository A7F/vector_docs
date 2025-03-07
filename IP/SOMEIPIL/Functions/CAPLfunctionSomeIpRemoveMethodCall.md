[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpRemoveMethodCall.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpRemoveMethodCall**

# SomeIpRemoveMethodCall

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
LONG SomeIpRemoveMethodCall( dword methodHandle );
```

## Description

Removes a method call of the Consumed Service Instance. The method was previously added by [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md).

Afterwards the method handle is no longer valid and cannot be used anymore with [SomeIpCallMethod](CAPLfunctionSomeIpCallMethod.md).

## Parameters

- **methodHandle**: Handle of the method.

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters **Member_value1** and **Member_value2**, and a return parameter **Result**.

```plaintext
variables
{
  DWORD gMc; // global method call handle
}

on key 'e'
{
  DWORD csi; // consumed Service Instance handle
  DWORD mc;  // method call

  // open Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(0x11, 50002);
  csi = SomeIpCreateConsumedServiceInstance(aep,11,1);

  // create method call
  gMc = SomeIpCreateMethodCall(csi,31,"OnMethodResponse");

  // set the two input parameters of the method and call the method
  SomeIpSetValueDWord(gMc,"Member_value1",11);
  SomeIpSetValueDWord(gMc,"Member_value2",22);
  SomeIpCallMethod(gMc);
}

on key 'r'
{
  // remove method call
  SomeIpRemoveMethodCall(gMc);
}

void OnMethodResponse(dword methodCallHandle, dword messageResponseHandle )
{
  DWORD res; // value of return parameter

  // get the returned parameter values
  res = SomeIpGetValueDWord(messageResponseHandle,"Result");

  write("The method call returned value: %d",res);
}
```

[See Also](javascript:void(0);)
```markdown