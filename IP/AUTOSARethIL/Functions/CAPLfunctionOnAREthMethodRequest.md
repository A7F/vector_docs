[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthMethodRequest.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » `<OnAREthMethodRequest>`

# `<OnAREthMethodRequest>`

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `void <OnAREthMethodRequest>(dword methodHandle, dword messageHandle, dword messageResponseHandle); // form 1`
- `void <OnAREthMethodRequest>(dword methodHandle, dword messageHandle); // form 2`
- `long <OnAREthMethodRequest>(dword methodHandle, dword messageHandle, dword messageResponseHandle); // form 3`

## Description

A callback function with this signature must be passed to the CAPL function [AREthAddMethod](CAPLfunctionAREthAddMethod.md).

**Note:** The syntax of the callback function specified in form 2 must be used if the **fireAndForget** parameter was used when the method was created by the provider (see also [AREthAddMethod](CAPLfunctionAREthAddMethod.md)).

This callback is called when a consumer has called the method created with [AREthAddMethod](CAPLfunctionAREthAddMethod.md).

## Parameters

- **methodHandle**: Handle of the Event that triggered the callback, see [AREthAddMethod](CAPLfunctionAREthAddMethod.md).
- **messageHandle**: Message handle of the SOME/IP request. The message contains the parameter values specified by the consumer in the method call.

  **Note:**
  - If the getter method of a field was overwritten (see also [AREthAddField](CAPLfunctionAREthAddField.md)), the SOME/IP message payload of the request is empty.
  - If the setter method of a field was overwritten (see also [AREthAddField](CAPLfunctionAREthAddField.md)), the SOME/IP message contains the current field content.

- **messageResponseHandle**: Message handle of the SOME/IP response. The result of the method call must be saved in this message. All parameters of this message are initialized with 0 by default and can be changed using [AREthSetValue...](CAPLfunctionAREthSetValue.md). When this callback method is exited, this SOME/IP message is sent.

  **Note:**
  - If the getter method of a field was overwritten (see also [AREthAddField](CAPLfunctionAREthAddField.md)), the SOME/IP response message contains the field content. The content of this SOME/IP message can be changed using [AREthSetValue...](CAPLfunctionAREthSetValue.md). These changes have no effect on the field content itself when this callback method is exited.
  - If the setter method of a field was overwritten (see also [AREthAddField](CAPLfunctionAREthAddField.md)), the SOME/IP response message already contains the new field content. The content of this SOME/IP message can be changed using [AREthSetValue...](CAPLfunctionAREthSetValue.md). When this callback method is exited, the current field content is automatically overwritten with the field content of the SOME/IP response message.

## Return Values

- **Form 1, 2**: —
- **Form 3**: The response will be sent if the callback returns 1. Otherwise, the response has been filtered by the callback.

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters (**Member_value1** and **Member_value2**), and a return parameter (**Result**).

```plaintext
variables
{
  dword gPm; // provided method handle
}

void Initialize()
{
  dword aep; // application endpoint handle
  dword psi; // provided Service Instance handle

  // open application endpoint
  aep = AREthOpenLocalApplicationEndpoint(17, 50002);

  // create Service Instance
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
  val1 = (WORD)AREthGetValueDWord(messageHandle,"Member_value1");
  val2 = (WORD)AREthGetValueDWord(messageHandle,"Member_value2");

  // calculate result
  res = val1 + val2;

  // set response value
  AREthSetValueDWord(messageResponseHandle,"Result",(val1 + val2));
}
```

[See Also](javascript:void(0);)