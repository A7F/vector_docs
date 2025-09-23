# SLACGenerateApplyKey

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
MethodReturnValueType SLACGenerateApplyKey ();
MethodReturnValueType SLACGenerateApplyKey (string targetMacAddress);
```

## Description

Immediately sends a **CM_Set_Key.Req** message with a new NMK and NID. If a target address is transferred, it is saved as a new PLC chip MAC address and used for all further messages to the PLC chip.

## Parameters

- **targetMacAddress**: MAC address as string with colon as separator between the bytes.

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

## Example

```plaintext
on key 'x'
{
  EVSE.SLACGenerateApplyKey.Call();
}

on key 'y'
{
  char newPLCMacAddress[18] = "02:00:00:00:FF:01";

  EVSE.SLACGenerateApplyKey.Call(newPLCMacAddress);
}
```
