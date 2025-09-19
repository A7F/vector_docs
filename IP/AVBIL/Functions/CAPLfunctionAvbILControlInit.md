[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbILControlInit.md)

**CAPL Functions** » **Ethernet** » **AVB IL** » **AvbILControlInit**

# AvbILControlInit

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword AvbILControlInit();
```

## Description

Initialization of the AVB IL.

Initializes, but prevents the AVB IL, i.e. the simulated time aware end station (PTP clock instance), from starting automatically. If this function is used, the AVB IL must then be started with the [AvbILControlStart](CAPLfunctionAvbILControlStart.md) function.

This function may only be used in `on preStart`.

## Parameters

—

## Return Values

- **0**: The function was successfully executed.
- **>0**: [Error code](../CAPLfunctionsAVBILErrorCode.md)

## Example

—

[See Also](javascript:void(0);)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
