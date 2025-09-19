[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthCreateMethodCall.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthCreateMethodCall**

# AREthCreateMethodCall

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword AREthCreateMethodCall( dword csiHandle, dword methodId, char OnAREthMethodResponse [] ); // form 1`
- `dword AREthCreateMethodCall( dword csiHandle, dword methodId ); // form 2`
- `dword AREthCreateMethodCall( dword csiHandle, dword methodId, char OnAREthMethodResponse [], char OnAREthMethodError []); // form 3`

## Description

This function creates a method call for the consumer. By means of the return value of the function, the method parameters can be set using [AREthSetValue...](CAPLfunctionAREthSetValue.md). The method is then called using [AREthCallMethod](CAPLfunctionAREthCallMethod.md).

**Note:** If the function is called with the syntax specified in form 1, the method call takes place asynchronously. At the same time, the client is not blocked after the method call until the corresponding response. A synchronous method call is not supported by AUTOSAR Eth IL.

The syntax specified in form 2 must be used if the **fireAndForget** parameter was used when the method was created for the provider (see also [AREthAddMethod](CAPLfunctionAREthAddMethod.md)).

The method call can be removed again using the [AREthRemoveMethodCall](CAPLfunctionAREthRemoveMethodCall.md) function.

## Parameters

- **csiHandle**: Handle of the Consumed Service Instance that was created by [AREthCreateConsumedServiceInstance](CAPLfunctionAREthCreateConsumedServiceInstance.md).
- **methodId**: Identifier of the method
- **onResponseCallback**: This callback function is called when the response is received, see [`<OnAREthMethodResponse>`](CAPLfunctionOnAREthMethodResponse.md)
- **onErrorCallback**: This callback function is called when a SomeIp error message is received, see [`<OnAREthMethodError>`](CAPLfunctionOnAREthMethodError.md)

## Return Values

- **0**: An error occurred. The error can be evaluated using the [AREthGetLastError](CAPLfunctionAREthGetLastError.md) function.
- **>0**: Handle to the method call.

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters **Member_value1** and **Member_value2**, and a return parameter **Result**.

```plaintext
variables
{
  dword gMc; // global method call handle
}

void Initialize()
{
  dword aep; // Application Endpoint handle
  dword csi; // consumed Service Instance handle

  // open Application Endpoint
  aep = AREthOpenLocalApplicationEndpoint(0x11, 50002);

  // create Service Instance
  csi = AREthCreateConsumedServiceInstance(aep,11,1);

  // create method call
  gMc = AREthCreateMethodCall(csi,31,"OnMethodResponse");
}

on key 's'
{
  // if this key is pressed the method should be called

  // set the two input parameters of the method
  AREthSetValueDWord(gMc,"Member_value1",11);
  AREthSetValueDWord(gMc,"Member_value2",22);

  // call the method
  AREthCallMethod(gMc);
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
