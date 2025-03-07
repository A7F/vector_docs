[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionOnSomeIpMethodRequest.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » `<OnSomeIpMethodRequest>`

# `<OnSomeIpMethodRequest>`

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `void <OnSomeIpMethodRequest>(dword methodHandle, dword messageHandle, dword messageResponseHandle); // form 1`
- `void <OnSomeIpMethodRequest>(dword methodHandle, DWORD messageHandle); // form 2`
- `long <OnSomeIpMethodRequest>(dword methodHandle, dword messageHandle, dword messageResponseHandle); // form 3`

## Description

A callback function with this signature must be passed to the CAPL function [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md).

**Note:** The syntax of the callback function specified in form 2 must be used if the **fireAndForget** parameter was used when the method was created by the provider (see also [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md)).

This callback is called when a consumer has called the method created with [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md).

## Parameters

- **methodHandle**: Handle of the Event that triggered the callback, see [SomeIpAddMethod](CAPLfunctionSomeIpAddMethod.md).
- **messageHandle**: Message handle of the SOME/IP request. The message contains the parameter values specified by the consumer in the method call.

  **Note:**
  - If the getter method of a field was overwritten (see also [SomeIpAddField](CAPLfunctionSomeIpAddField.md)), the SOME/IP message payload of the request is empty.
  - If the setter method of a field was overwritten (see also [SomeIpAddField](CAPLfunctionSomeIpAddField.md)), the SOME/IP message contains the current field content.

- **messageResponseHandle**: Message handle of the SOME/IP response. The result of the method call must be saved in this message. All parameters of this message are initialized with 0 by default and can be changed using [SomeIpSetValue...](CAPLfunctionSomeIpSetValue.md). When this callback method is exited, this SOME/IP message is sent.

  **Note:**
  - If the getter method of a field was overwritten (see also [SomeIpAddField](CAPLfunctionSomeIpAddField.md)), the SOME/IP response message contains the field content. The content of this SOME/IP message can be changed using [SomeIpSetValue...](CAPLfunctionSomeIpSetValue.md). These changes have no effect on the field content itself when this callback method is exited.
  - If the setter method of a field was overwritten (see also [SomeIpAddField](CAPLfunctionSomeIpAddField.md)), the SOME/IP response message already contains the new field content. The content of this SOME/IP message can be changed using [SomeIpSetValue...](CAPLfunctionSomeIpSetValue.md). When this callback method is exited, the current field content is automatically overwritten with the field content of the SOME/IP response message.

## Return Values

- Form 1, 2: —
- Form 3: The response will be sent if the callback returns 1. Otherwise, the response has been filtered by the callback.

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters (**Member_value1** and **Member_value2**), and a return parameter (**Result**).

```plaintext
variables
{
  DWORD gPm; // provided method handle
}

void Initialize()
{
  DWORD aep; // application endpoint handle
  DWORD psi; // provided Service Instance handle

  // open application endpoint
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