[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpCallMethod.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpCallMethod**

# SomeIpCallMethod

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
LONG SomeIpCallMethod( dword methodHandle );
```

## Description

Initiates a method call by sending a request to the server. The service that the method contains must be offered by the provider through an Offer Service message and still be valid so that the method can be successfully called.

**Background:**

For a successful method call, the remote address and the remote port of the provided service is needed. This is communicated via the Offer Service message.

## Parameters

- **methodHandle**: Handle of the method call that was created by [SomeIpCreateMethodCall](CAPLfunctionSomeIpCreateMethodCall.md).

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

void Initialize()
{
  DWORD aep; // application endpoint handle
  DWORD csi; // consumed Service Instance handle

  // open application endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(0x11, 50002);

  // cretae Service Instance
  csi = SomeIpCreateConsumedServiceInstance(aep,11,1);

  // create method call
  gMc = SomeIpCreateMethodCall(csi,31,"OnMethodResponse");
}

on key 's'
{
  // if this key is pressed the method should be called

  // set the two input parameters of the method
  SomeIpSetValueDWord(gMc,"Member_value1",11);
  SomeIpSetValueDWord(gMc,"Member_value2",22);

  // call the method
  SomeIpCallMethod(gMc);
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
