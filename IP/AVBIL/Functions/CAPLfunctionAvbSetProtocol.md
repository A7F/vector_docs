[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbSetProtocol.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbSetProtocol**

# AvbSetProtocol

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword AvbSetProtocol(dword talkerHandle, dword protocol);
```

## Description

The function sets the AVTP protocol of the Talker.

## Parameters

- **talkerHandle**: The handle of the Talker.
- **protocol**: The AVTP protocol to be set. The currently supported protocols are:
  - **0x02**: AAF (AVTP Audio Format)
  - **0x04**: CRF (Clock Reference Format)

## Return Values

- **0**: The function completed successfully.
- **>0**: [Error code](../../CAPLfunctionsIPErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)
