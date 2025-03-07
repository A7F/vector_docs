[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/CAPLfunctionsCANoeILOverview.md)

[CAPL Functions](../CAPLfunctions.md) » CANoe IL CAPL Functions

# CANoe IL CAPL Functions

**Valid for**:  CANoe DE • CANoe4SW DE

The following functions are available with the CANoe Interaction Layer (CANoe IL) and included [CANoeILNLVector.vmodule.](../../CANoeCANalyzer/LibrariesPackages/VectorILCAN/VectorILCAN.md) These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet. Not all functions are supported by ERT, see **ERT Support** column.

**ON THIS PAGE:**

- [Callback Interface](#CallbackInterface)
- [Control](#Control)
- [Fault Injection and Disturbance](#FaultInjectionAndDisturbance)
- [Functions for Test Setup and Simulation Setup](#TestSetupSimulationSetup)
- [Maintenance](#Maintenance)
- [Message Handling](#MessageHandling)
- [OEM Add-ons Based on Fault Injection Functions](#OEMPackageFaultInjection)
- [Signal Handling](#SignalHandling)

## Callback Interface [▲ back]

| Functions | ERT Support | Short Description |
|-----------|-------------|-------------------|
| [applILTxPending](Functions/CAPLfunctionApplILTxPending.md) | ✔ | This callback is optionally being called before the IL sends a message to the bus. |
| [applILTxRequestConsumed](Functions/CAPLfunctionApplILTxRequestConsumed.md) | — | After the IL clamp 15 state has been enabled by [ILActivateClamp15](Functions/CAPLfunctionILActivateClamp15.md) or any wake-up-allowed signal is transmitted, then optionally this functions is called. |
| [applILTxRequestPending](Functions/CAPLfunctionApplILTxRequestPending.md) | — | If the IL clamp 15 state is being enabled by [ILActivateClamp15](Functions/CAPLfunctionILActivateClamp15.md) or any wake-up-allowed signal is changed, then optionally this functions is called. |

## Control [▲ back]

| Functions | ERT Support | Short Description |
|-----------|-------------|-------------------|
| [ILActivateClamp15](Functions/CAPLfunctionILActivateClamp15.md) | — | Forwards the appropriate state of clamp 15. |
| [ILConfigureNMNotifications](Functions/CAPLfunctionILConfigureNMNotifications.md) | — | Allows manipulating the coupling between IL and NM module. |
| [ILControlInit](Functions/CAPLfunctionILControlInit.md) | ✔ | Initialization of CANoe IL. |
| [ILControlResume](Functions/CAPLfunctionILControlResume.md) | ✔ | Cyclical sending restarts. |
| [ILControlSimulationOff](Functions/CAPLfunctionILControlSimulationOff.md) | ✔ | Stops the simulation of the IL. |
| [ILControlSimulationOn](Functions/CAPLfunctionILControlSimulationOn.md) | ✔ | Starts the simulation of the IL. |
| [ILControlStart](Functions/CAPLfunctionILControlStart.md) | ✔ | Cyclical sending starts; setting signals is now possible. |
| [ILControlStop](Functions/CAPLfunctionILControlStop.md) | ✔ | Cyclical sending is stopped; setting signals is now no longer possible. |
| [ILControlWait](Functions/CAPLfunctionILControlWait.md) | ✔ | Cyclical sending is stopped; setting signals is possible. |
| [ILDeactivateClamp15](Functions/CAPLfunctionILActivateClamp15.md) | — | Forwards the appropriate state of clamp 15. |
| [ILSetAutoStartParam](Functions/CAPLfunctionILILSetAutoStartParam.md) | ✔ | Defines the behavior of the interaction layer at the start of measurement. |

## Fault Injection and Disturbance [▲ back]

| Functions | ERT Support | Short Description |
|-----------|-------------|-------------------|
| [ILFaultInjectionDisableMsg](Functions/CAPLfunctionILFaultInjectionDisableMsg.md) | ✔ | Prevents all sending of the message except the sending by calling the function [ILSetMsgEvent](Functions/CAPLfunctionILSetMsgEvent.md). |
| [ILFaultInjectionEnableMsg](Functions/CAPLfunctionILFaultInjectionEnableMsg.md) | ✔ | Enables the sending of the message. |
| [ILFaultInjectionResetAllFaultInjections](Functions/CAPLfunctionILFaultInjectionResetAllFaultInjections.md) | ✔ | Reset all fault injection settings. |
| [ILFaultInjectionResetMsgCycleTime](Functions/CAPLfunctionILFaultInjectionResetMsgCycleTime.md) | ✔ | Resets the cycle time of the message to the database cycle time. |
| [ILFaultInjectionResetMsgDlc](Functions/CAPLfunctionILFaultInjectionResetMsgDlc.md) | ✔ | Resets the DLC of the message to the database DLC. |
| [ILFaultInjectionResetMsgLength](Functions/CAPLfunctionILFaultInjectionResetMsgLength.md) | ✔ | Resets the message length (in bytes) of the message to the database. |
| [ILFaultInjectionSetMsgCycleTime](Functions/CAPLfunctionILFaultInjectionSetMsgCycleTime.md) | ✔ | Assigns a new cycle time to the message. |
| [ILFaultInjectionSetMsgDlc](Functions/CAPLfunctionILFaultInjectionSetMsgDlc.md) | ✔ | Assigns a new DLC to the message. |
| [ILFaultInjectionSetMsgLength](Functions/CAPLfunctionILFaultInjectionSetMsgLength.md) | ✔ | Assigns a new message length (in bytes) to the message. |

## Functions for Test Setup and Simulation Setup [▲ back]

Various control and disturbance functions are provided for implementing a central control node in the Simulation Setup or tests in the CAPL test module.

| Functions | ERT Support | Short Description |
|-----------|-------------|-------------------|
| [ILNodeControlMsg](Functions/CAPLfunctionILNodeControlMsg.md) | — | Influences the sending of a certain message of a simulation node with an assigned interaction layer. |
| [ILNodeControlResume](Functions/CAPLfunctionILNodeControlResume.md) | — | Restarts cyclical sending. |
| [ILNodeControlSimulationOff](Functions/CAPLfunctionILNodeControlSimulationOff.md) | — | Stops the simulation of the interaction layer. |
| [ILNodeControlSimulationOn](Functions/CAPLfunctionILNodeControlSimulationOn.md) | — | Starts the simulation of the interaction layer. |
| [ILNodeControlStart](Functions/CAPLfunctionILNodeControlStart.md) | — | Starts cyclical sending. Setting of signals is possible again. |
| [ILNodeControlStop](Functions/CAPLfunctionILNodeControlStop.md) | — | Stops cyclical sending. Setting of signals is not possible anymore. |
| [ILNodeControlWait](Functions/CAPLfunctionILNodeControlWait.md) | — | Stops cyclical sending. Setting of signals is still possible. |
| [ILNodeDisturbAllNodesUpdateBits](Functions/CAPLfunctionILNodeDisturbAllNodesUpdateBits.md) | — | Modifies all update bits of signals/signal groups of all nodes in the current bus context. |
| [ILNodeDisturbAllUpdateBits](Functions/CAPLfunctionILNodeDisturbAllUpdateBits.md) | — | Modifies all update bits of signals/signal groups of a node. |
| [ILNodeDisturbChecksum](Functions/CAPLfunctionILNodeDisturbChecksum.md) | — | Disturbs the checksum a configurable value. |
| [ILNodeDisturbCounter](Functions/CAPLfunctionILNodeDisturbCounter.md) | — | Disturbs the counter with a configurable value. |
| [ILNodeDisturbPduUpdateBit](Functions/CAPLfunctionILNodeDisturbPduUpdateBit.md) | — | Modifies the update bit of a signal group. |
| [ILNodeDisturbSignalGroupUpdateBit](Functions/CAPLfunctionILNodeDisturbSignalGroupUpdateBit.md) | — | Disturbs the signal update bit with a configurable value. |
| [ILNodeDisturbSignalUpdateBit](Functions/CAPLfunctionILNodeDisturbSignalUpdateBit.md) | — | Disturbs the PDU Update Bit with constant 0 or 1. |
| [ILNodeSetAllNodesOperationMode](Functions/CAPLfunctionILNodeSetAllNodesOperationMode.md) | — | Sets specific operation mode in the interaction layer of all nodes. |
| [ILNodeSetOperationMode](Functions/CAPLfunctionILNodeSetOperationMode.md) | — | Sets specific operation mode in the interaction layer. |
| [ILNodeSetSigGroupOperationMode](Functions/CAPLfunctionILNodeSetSigGroupOperationMode.md) | — | Sets specific operation mode in the interaction layer for a specified signal group. |
| [ILNodeSetPDUTimingCyclic](Functions/CAPLfunctionILNodeSetPDUTimingCyclic.md) | — | Overrides the defined cyclic-timing from the database. |
| [ILNodeResetPDUTimingCyclic](Functions/CAPLfunctionILNodeResetPDUTimingCyclic.md) | — | Resets the cyclic-timing to the values from the database. |
| [ILNodeSetPDUTimingEvent](Functions/CAPLfunctionILNodeSetPDUTimingEvent.md) | — | Overrides the defined event timing from the database. |
| [ILNodeResetPDUTimingEvent](Functions/CAPLfunctionILNodeResetPDUTimingEvent.md) | — | Resets the event-timing to the values from the database. |
| [ILNodeSetPDUAsrTxMode](Functions/CAPLfunctionILNodeSetPDUAsrTxMode.md) | — | Overrides the current valid transmission mode of the PDU. |
| [ILNodeResetPDUAsrTxMode](Functions/CAPLfunctionILNodeResetPDUAsrTxMode.md) | — | Resets the current valid transmission mode to the condition that is defined by or-ing all data filters of all signals. |

## Maintenance [▲ back]

| Functions | ERT Support | Short Description |
|-----------|-------------|-------------------|
| [ILErrno](Functions/CAPLfunctionILErrno.md) | ✔ | Returns the last CANoe IL error code. |
| [ILSetResultString](Functions/CAPLfunctionILSetResultString.md) | ✔ | Converts the transferred error code to text. |

## Message Handling [▲ back]

| Functions | ERT Support | Short Description |
|-----------|-------------|-------------------|
| [ILControlMsg](Functions/CAPLfunctionILControlMsg.md) | ✔ | Allows to manipulate the sending behavior of a message. |
| [ILResetAllCANFDParam](Functions/CAPLfunctionILResetAllCANFDParam.md) | ✔ | Resets CAN FD parameters of all messages to database values. |
| [ILSetCANFDParam](Functions/CAPLfunctionILSetCANFDParam.md) | ✔ | Allows setting of CAN FD parameters for a specific message. |
| [ILSetMsgEvent](Functions/CAPLfunctionILSetMsgEvent.md) | — | Sends the transferred message directly to the bus if the network is active. |

## OEM Add-on Based on Fault Injection Functions [▲ back]

CAN or FlexRay Specific Functions for Simulation Setup

| Functions | ERT Support | Short Description |
|-----------|-------------|-------------------|
| [ILCalculateChecksum](Functions/CAPLfunctionILCalculateChecksum.md) | — | Calculates the corresponding CRC checksum based on the payload. |
| [ILDisableMSG](Functions/CAPLfunctionILDisableMsg.md) | — | Disables the sending of the message except by calling the function [ILSetMsgEvent](Functions/CAPLfunctionILSetMsgEvent.md). |
| [ILEnableMSG](Functions/CAPLfunctionILEnableMsg.md) | — | Enables the sending of the message. |
| [ILEnableTimingCyclic](Functions/CAPLfunctionILEnableTimingCyclic.md) | — | Controls the cyclic timing of PDUs. The cyclic timing can be enabled/disabled. |
| [ILEnableTimingEvtTrg](Functions/CAPLfunctionILEnableTimingEvtTrg.md) | — | Controls the event triggered timing of PDUs. The event triggered timing can be enabled/disabled. |
| [ILEnableTimingImmed](Functions/CAPLfunctionILEnableTimingImmed.md) | — | Controls the immediate timing of PDUs. The immediate timing can be enabled/disabled. |

## Signal Handling [▲ back]

| Functions | ERT Support | Short Description |
|-----------|-------------|-------------------|
| [ILSetEvent](Functions/CAPLfunctionILSetEvent.md) | — | Sends the transferred signal directly to the bus if the network is active. |
| [ILSetSignalRawField](Functions/CAPLfunctionILSetSignalRawField.md) | — | Sets the transferred signal to the provided value. |

[CANoe Interaction Layer (CAN)](../../CANoeCANalyzer/LibrariesPackages/VectorILCAN/VectorILCAN.md) • [Return Codes](../../CANoeCANalyzer/LibrariesPackages/VectorILCAN/VectorILCANErrorCodes.md) • [Test Feature Set CAPL Functions](../Test/CAPLfunctionsTFSOverview.md#OEMPackageFaultInjection) • [Functions in the Execution Context](CAPLfunctionsCANoeILOverviewExecContext.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)