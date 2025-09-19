# AUTOSAR PDU IL CAPL Functions

**Valid for:** CANoe DE • CANoe4SW DE

The functions are available with the AUTOSAR PDU Interaction Layer (AUTOSAR PDU IL) and included [AsrPDUIL2.vmodule.](../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduIL.md) These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet. When using **ASRPDUIL.vmodule** instead of **ASRPDUIL2.vmodule**, all CAPL functions have the prefix **IL** instead of **ARIL**. See [AUTOSAR PDU Interaction Layer](../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduIL.md).

---

**ON THIS PAGE:**

- [Callback Interface](#CallbackInterface)
- [Control](#Control)
- [Fault Injection and Disturbance](#FaultInjectionAndDisturbance)
- [Maintenance](#Maintenance)
- [Message Handling](#MessageHandling)
- [Signal Handling](#SignalHandling)
- [Timing Modification](#TimingModification)

## Callback Interface [▲ back](#Shortcuts)

| Functions | Short Description |
|-----------|-------------------|
| [applPDUilTxPending](Functions/CAPLfunctionApplPDUilTxPending.md) | This callback is optionally being called before the IL sends a PDU to the bus. |
| [applILTxRequestConsumed](../CANoeIL/Functions/CAPLfunctionApplILTxRequestConsumed.md) | After **Ignition** state has been enabled by [ARILSetIgnitionState](Functions/CAPLfunctionARILSetIgnitionState.md) or any wake-up-allowed signal is transmitted, then optionally this function is called. |
| [applILTxRequestPending](../CANoeIL/Functions/CAPLfunctionApplILTxRequestPending.md) | If the **Ignition** state is being enabled by [ARILSetIgnitionState](Functions/CAPLfunctionARILSetIgnitionState.md) or any wake-up-allowed signal is changed, then optionally this function is called. |

## Control [▲ back](#Shortcuts)

| Functions | Short Description |
|-----------|-------------------|
| [ARILConfigureNMNotifications](Functions/CAPLfunctionARILConfigureNMNotifications.md) | This function has impact on the (automatic) coupling between IL and NM on the IL side. |
| [ARILControlInit](Functions/CAPLfunctionARILControlInit.md) | Initializes the IL. If this function is called in [on preStart](../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md), then the IL will enter the **suspended** state during [on Start](../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) and must explicitly be started. |
| [ARILControlResume](Functions/CAPLfunctionARILControlResume.md) | Resumes a suspended IL and starts sending PDUs again. |
| [ARILControlSimulationOff](Functions/CAPLfunctionARILControlSimulationOff.md) | Stops the simulation of the IL. The IL is not operational. All API function except function [ARILControlSimulationOn](Functions/CAPLfunctionARILControlSimulationOn.md) will not work. |
| [ARILControlSimulationOn](Functions/CAPLfunctionARILControlSimulationOn.md) | Starts the simulation of the IL. The IL is operational and started. The IL will send PDUs. |
| [ARILControlStart](Functions/CAPLfunctionARILControlStart.md) | When the IL is started, then it is fully operating and sending. |
| [ARILControlStop](Functions/CAPLfunctionARILControlStop.md) | Stops sending of PDUs. |
| [ARILControlPDU](Functions/CAPLfunctionARILControlPDU.md) | Sets/activates/deactivates a special feature/action for a dedicated PDU. |
| [ARILControlWait](Functions/CAPLfunctionARILControlWait.md) | Stops sending, but accepts signal changes. |
| [ARILSetAutoStartParam](Functions/CAPLfunctionARILILSetAutoStartParam.md) | This function influences the start behavior. |
| [ARILSetIgnitionState](Functions/CAPLfunctionARILSetIgnitionState.md) | Activates or deactivates the ignition status globally. |
| [ARILSetOperationMode](Functions/CAPLfunctionARILSetOperationMode.md) | Influences the behavior of the update bits and counters. |
| [ARILSetPowerState](Functions/CAPLfunctionARILSetPowerState.md) | Activates or deactivates the power status globally. |

## Fault Injection and Disturbance [▲ back](#Shortcuts)

| Functions | Short Description |
|-----------|-------------------|
| [ARILFaultInjectionDisableAllTxPDU](Functions/CAPLfunctionARILFaultInjectionDisableAllTxPDU.md) | Disables the sending of all PDUs of the current node instance. |
| [ARILFaultInjectionDisablePDU](Functions/CAPLfunctionARILFaultInjectionDisablePDU.md) | Disables the sending of the PDU except by calling the function [ARILSetPDUEvent](Functions/CAPLfunctionARILSetPDUEvent.md). |
| [ARILFaultInjectionDisturbChecksum](Functions/CAPLfunctionARILFaultInjectionDisturbChecksum.md) | Disturbs the CRC of a PDU or signal group (see [CRC Value](../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILFeatures.md#CRCValue)). |
| [ARILFaultInjectionDisturbNodeUpdateBits](Functions/CAPLfunctionARILFaultInjectionDisturbNodeUpdateBits.md) | Disturbs the Update Bit of all signals and/or signal groups that are sent by the current node (see [Update Bit](../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILFeatures.md#UpdateBit)). |
| [ARILFaultInjectionDisturbSequenceCounter](Functions/CAPLfunctionARILFaultInjectionDisturbSequenceCounter.md) | Disturbs the SQC or TGL of a PDU or signal group (see [Supported Features](../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILFeatures.md)). |
| [ARILFaultInjectionDisturbUpdateBit](Functions/CAPLfunctionARILFaultInjectionDisturbUpdateBit.md) | Disturbs the Update Bit of a signal or signal group (see [Update Bit](../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILFeatures.md#UpdateBit)). |
| [ARILFaultInjectionEnableAllTxPDU](Functions/CAPLfunctionARILFaultInjectionEnableAllTxPDU.md) | Enables the sending of all PDUs of the current node instance. |
| [ARILFaultInjectionEnablePDU](Functions/CAPLfunctionARILFaultInjectionEnablePDU.md) | Enables the sending of the PDU. |
| [ARILFaultInjectionResetAllFaultInjections](Functions/CAPLfunctionARILFaultInjectionResetAllFaultInjections.md) | Resets the fault injection settings for all PDUs of the node. |
| [ARILFaultInjectionResetPDULength](Functions/CAPLfunctionARILFaultInjectionResetPDULength.md) | Resets the payload length back to its original value from the database. |
| [ARILFaultInjectionSetIgnitionState](Functions/CAPLfunctionARILFaultInjectionSetIgnitionState.md) | Activates or deactivates the ignition status locally. |
| [ARILFaultInjectionSetPDULength](Functions/CAPLfunctionARILFaultInjectionSetPDULength.md) | Sets a new payload length for the PDU. |
| [ARILFaultInjectionSetPowerState](Functions/CAPLfunctionARILFaultInjectionSetPowerState.md) | Activates or deactivates the power status locally. |

## Maintenance [▲ back](#Shortcuts)

| Functions | Short Description |
|-----------|-------------------|
| [ARILCalculateCRC](Functions/CAPLfunctionARILCalculateCRC.md) | Calculates the CRC of the PDU according to the given payload. |
| [ARILGetSigGroupCount](Functions/CAPLfunctionARILGetSigGroupCount.md) | Evaluates how many signal groups are defined inside the PDU. |
| [ARILGetSigGroupName](Functions/CAPLfunctionARILGetSigGroupName.md) | Retrieves the name of the n`<sup>`th</sup> signal group of the PDU. |

## Message Handling [▲ back](#Shortcuts)

| Functions | Short Description |
|-----------|-------------------|
| [ARILSetPDUEvent](Functions/CAPLfunctionARILSetPDUEvent.md) | A call of this function will lead to a transmission of the associated PDU. |
| [ARILControlPDU](Functions/CAPLfunctionARILControlPDU.md) | Sets/activates/deactivates a special feature/action for a dedicated PDU. |

## Signal Handling [▲ back](#Shortcuts)

| Functions | Short Description |
|-----------|-------------------|
| [ARILSetEvent](Functions/CAPLfunctionARILSetEvent.md) | This function considers **Debounce Delay**, and it also considers the activity of the network. |

## Timing Modification [▲ back](#Shortcuts)

| Functions | Short Description |
|-----------|-------------------|
| [ARILResetPDUAsrTXMode](Functions/CAPLfunctionARILResetPDUAsrTXMode.md) | Resets the current valid transmission mode to the condition that is defined by or-ing all data filters of all signals. |
| [ARILResetPDUTimingCyclic](Functions/CAPLfunctionARILResetPDUTimingCyclic.md) | Resets the **cyclic-timing** to the values from the database. |
| [ARILResetPDUTimingEvent](Functions/CAPLfunctionARILResetPDUTimingEvent.md) | Resets the **event-timing** to the values from the database. |
| [ARILSetPDUAsrTXMode](Functions/CAPLfunctionARILSetPDUAsrTXMode.md) | Overrides the current valid transmission mode of the PDU. |
| [ARILSetPDUTimingCyclic](Functions/CAPLfunctionARILSetPDUTimingCyclic.md) | Overrides the defined **cyclic-timing** from the database. |
| [ARILSetPDUTimingEvent](Functions/CAPLfunctionARILSetPDUTimingEvent.md) | Overrides the defined **event-timing** from the database. |

[AUTOSAR PDU Interaction Layer](../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduIL.md) • [Return Codes](../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) • [Test Feature Set CAPL Functions](../Test/CAPLfunctionsTFSOverview.md#OEMPackageFaultInjection)
