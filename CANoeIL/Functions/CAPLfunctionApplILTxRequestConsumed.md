# applILTxRequestConsumed

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Note**  
The CAPL program may define these optional functions (all marked with the prefix **appl**) to receive indications about events from the IL.

## Function Syntax

```plaintext
void applILTxRequestConsumed ( );
```

## Description

After the **IL clamp 15** state (for [ASR PDU IL](../../AUTOSARpduIL/CAPLfunctionsAUTOSARpduILOverview.md) **Ignition** state) has been enabled by [ILActivateClamp15](CAPLfunctionILActivateClamp15.md) (for ASR PDU IL [ARILSetIgnitionState](../../AUTOSARpduIL/Functions/CAPLfunctionARILSetIgnitionState.md)) or any wake-up-allowed signal is transmitted, then optionally this functions is called. Within this function the bus NM sleep timer should be restarted.

## Parameters

—

## Return Values

—

## Example

—
