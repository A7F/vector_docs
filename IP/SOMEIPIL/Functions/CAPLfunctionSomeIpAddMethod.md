[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpAddMethod.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpAddMethod**

# SomeIpAddMethod

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword SomeIpAddMethod( dword psiHandle, dword methodId, char onMethodRequestCallback[] ); // form 1
dword SomeIpAddMethod( dword psiHandle, dword methodId, char onMethodRequestCallback[], long fireAndForget); // form 2
```

## Description

This function adds a method to a Provided Service Instance that was created with [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md).

If this method is called by a client through a SOME/IP request, the specified CAPL callback function is called. Only one CAPL callback function can be registered for each method.

**Note**: If the function is added with the syntax specified in form 1, the method call by the client takes place asynchronously. At the same time, the calling client is not blocked after the method call until the corresponding response. A synchronous method call is not supported by SOME/IP IL.

A method can be removed again using the [SomeIpRemoveMethod](CAPLfunctionSomeIpRemoveMethod.md) function.

## Parameters

- **psiHandle**: Handle of the Provided Service Instance that was created by [SomeIpCreateProvidedServiceInstance](CAPLfunctionSomeIpCreateProvidedServiceInstance.md).
- **methodId**: Identifier of the method
- **onMethodRequestCallback**: Name of the CAPL callback function, see CAPL callback [<OnSomeIpMethodRequest>](CAPLfunctionOnSomeIpMethodRequest.md)
- **fireAndForget**: Specifies whether the provider is to send a response after the method call:
  - 1: A response is not sent
  - 0: A response is sent (default behavior)

## Return Values

- **0**: An error occurred. The error can be evaluated using the [SomeIpGetLastError](CAPLfunctionSomeIpGetLastError.md) function.
- **>0**: Handle of the created method

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters **Member_value1** and **Member_value2**, and a return parameter **Result**.

```plaintext
variables
{
  DWORD gPm; // provided method handle
}

void Initialize()
{
  DWORD aep; // Application Endpoint handle
  DWORD psi; // provided Service Instance handle

  // open Application Endpoint
  aep = SomeIpOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
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
  val1 = (WORD)SomeIpGetValueDWord(messageHandle,"Member_value1");
  val2 = (WORD)SomeIpGetValueDWord(messageHandle,"Member_value2");

  // calculate result
  res = val1 + val2;

  // set response value
  SomeIpSetValueDWord(messageResponseHandle,"Result",(val1 + val2));
}
```

[See Also](javascript:void(0);)