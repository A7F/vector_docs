[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthILControlInit.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthILControlInit

# AREthILControlInit

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthILControlInit();
```

## Description

Initialization of AUTOSAR Eth IL.

Prevents the AUTOSAR Eth IL from starting automatically. If this function is used, the AUTOSAR Eth IL must then be started with the [AREthILControlStart](CAPLfunctionAREthILControlStart.md) function.

This function may only be used in `on preStart`.

## Parameters

— 

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on preStart
{
  // prevent auto start
  AREthILControlInit();
}
```

[See Also](javascript:void(0);)