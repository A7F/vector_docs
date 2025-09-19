# ARILConfigureNMNotifications

[CAPL Functions](../../CAPLfunctions.md) » [AUTOSAR PDU IL](../CAPLfunctionsAUTOSARpduILOverview.md) » ARILConfigureNMNotifications

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`dword ARILConfigureNMNotifications (dword dir, dword mode);`

## Description

This function has impact on the (automatic) coupling between IL and NM on the IL side.

Normally, there exists an automatic notification between IL and NM. This can be broken by implementation of dedicated call-back functions for IL and NM. This function defines to take or ignore those notifications always, regardless of existing callbacks.

Remember, an appropriate function can also be called on NM side!

## Parameters

- **dir**: Defines which direction is to be influenced:
  - 0: IL->NM (Tx notifications of IL)
  - 1: NM -> IL (Rx notifications of NM)
  - Other values are reserved.

- **mode**: Defines if the notifications are issued or handled (according to the direction):
  - 0: Notifications are not generated (Tx) or incoming notifications (Rx) are ignored.
  - 1: Notifications will be generated (Tx); regardless of existing callback functions of the IL, and are always handled (Rx).
  - 2: Notifications will be generated (Tx) only when specific callback functions of the IL are not implemented, and are always handled (Rx). This is the default, when the function is not called.

## Return Values

- **0**: No error
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—
