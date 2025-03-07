[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthFillValues.md)

**CAPL Functions » Ethernet » AUTOSAR Eth IL » AREthFillValues**

# AREthFillValues

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthFillValues(dword objectHandle, char valuePath[], long startValue, long incValue, dword arrayLength, dword flags);
```

## Description

With `AREthFillValues` you can fill the fields of SOME/IP events, methods and fields with increasing values for test purposes. You can enable or disable optional fields. You can increase or decrease arrays to specified lengths.

Nested structures and arrays are processed in descending order. Complex structures can be filled with test data in one call.

With the parameter **valuePath** only certain fields within a SOME/IP event, method and field can be filled. If an empty string ("") is specified for **valuePath**, then the entire frame is filled.

## Parameters

- **objectHandle**: Handle to a AUTOSAR Eth IL object, which must be completely described in the AUTOSAR database. The following objects are supported:
  - Messages
  - Fields
  - Method calls: Handle to a method call that was created with [AREthCreateMethodCall](CAPLfunctionAREthCreateMethodCall.md).

- **valuePath**: Access path of the value to be set. Empty string ("") fills the whole message.

- **startValue**: Start value to fill the members. Flag 0x01 or 0x02 must be used.

- **incValue**: Increment the value for each member to fill. Flag 0x01 or 0x02 must be used.

- **arrayLength**: Resize dynamic arrays to this length. Flag 0x10 or 0x20 must be used.

- **flags**: Flags:
  - 0x01 - Set physical value
  - 0x02 - Set raw value
  - 0x04 - Enable optional members
  - 0x08 - Disable optional members
  - 0x10 - Extend arrays to size of 'arrayLength', if it is smaller than 'arrayLength'
  - 0x20 - Shrink arrays to size of 'arrayLength', if it is larger than 'arrayLength'

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
variables
{
  dword gTrafficSignDetectionEvent;
}

on start
{
  gTrafficSignDetectionEvent = AREthGetProvidedObjectHandle("CameraObjectDetection::TrafficSignDetection");
  AREthRegisterCallback(gTrafficSignDetectionEvent, "OnPrepareEvent_TrafficSignDetection");
}

void OnPrepareEvent_TrafficSignDetection(dword pevHandle, dword messageHandle)
{
  // fill event with increasing values from 1, activate optional fields and set array sizes to 10
  AREthFillValues(messageHandle, "", 1, 1, 10, 0x15);
}
```

[See Also](javascript:void(0);)