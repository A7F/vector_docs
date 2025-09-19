# applILTxRequestPending

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
The CAPL program may define these optional functions (all marked with the prefix **appl**) to receive indications about events from the IL.

## Function Syntax

`void applILTxRequestPending ( );`

## Description

If the **IL clamp 15** state (for [ASR PDU IL](../../AUTOSARpduIL/CAPLfunctionsAUTOSARpduILOverview.md)**Ignition** state) is being enabled by [ILActivateClamp15](CAPLfunctionILActivateClamp15.md) (for ASR PDU IL [ARILSetIgnitionState](../../AUTOSARpduIL/Functions/CAPLfunctionARILSetIgnitionState.md)) or any wake-up-allowed signal is changed, then optionally this function is called. Within this function the bus should be requested by the network management DLL.

## Parameters

—

## Return Values

—

## Example

—
