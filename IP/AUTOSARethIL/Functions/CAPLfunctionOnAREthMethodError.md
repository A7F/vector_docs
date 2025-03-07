[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionOnAREthMethodError.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » `<OnAREthMethodError>`

# `<OnAREthMethodError>`

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void <OnAREthMethodError>(dword methodCallHandle, dword messageErrorHandle);
```

## Description

A callback function with this signature must be passed to the CAPL function [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

## Parameters

- **methodCallHandle**: Handle of the Event that triggered the callback, see [AREthAddMethod](CAPLfunctionAREthAddMethod.md).
- **messageErrorHandle**: Message handle of the SOME/IP error.

## Return Values

—

## Example

In this example, it is assumed that the created method is contained in the FIBEX database that is assigned to the CANoe configuration. The method has the Method ID 31, two input parameters (**Member_value1** and **Member_value2**), and a return parameter (**Result**).

```plaintext
variables
{
  dword gMc; // global method call handle
}

void Initialize()
{
  dword aep; // application endpoint handle
  dword csi; // consumed Service Instance handle

  // open application endpoint
  aep = AREthOpenLocalApplicationEndpoint(0x11, 50002);

  // create Service Instance
  csi = AREthCreateConsumedServiceInstance(aep,11,1);

  // create method call
  gMc = AREthCreateMethodCall(csi,31,"OnMethodResponse", ,"OnMethodError");
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

void OnMethodError(dword methodCallHandle, dword messageErrorHandle )
{
  // do error handling here
}
```

[See Also](javascript:void(0);)