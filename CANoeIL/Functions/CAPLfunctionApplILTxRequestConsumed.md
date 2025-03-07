[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionApplILTxRequestConsumed.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » applILTxRequestConsumed

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)