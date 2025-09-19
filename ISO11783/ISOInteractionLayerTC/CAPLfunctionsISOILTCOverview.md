[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/CAPLfunctionsISOILTCOverview.md)

### ISO11783 Task Controller Interaction Layer
*(Only available with ISO11783!)*

**Valid for**: CANoe DE • CANoe4SW DE

To use the CAPL functions the **ISO11783_TC_IL.dll** i.e. [Task Controller Interaction Layer (TC IL)](../../../Shared/ISO11783/ISO11783ILTC.md) must be included.

---

**ON THIS PAGE:**

- [Callback Functions](#Callback)
- [DTC Support](#DiagnosticFunctions)
- [Node Control](#Node)
- [Other Functions](#Other)
- [Signal/Message Access](#Signal/M)
- [TC - Client Control](#TCClientControl)
- [TC - Fault Injection for Messages](#TCFaultInjection)
- [TC - Fault Injection for Transport Protocols](#TCFaultInjectionTP)
- [TC - Other Functions](#TCOtherFunctions)
- [TC - Peer Control](#TCPeerControl)
- [TC - Value Access](#TCValueAccess)

---

#### Callback Functions 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_OnAddressClaimConflict](Functions/CAPLfunctionIso11783TCILOnAddressClaimConflict.md) | Is called if an address conflict is detected. |
| [TCIL_OnAddressViolation](Functions/CAPLfunctionIso11783TCILOnAddressViolation.md) | Is called if an address violation is detected. |
| [TCIL_OnCA](Functions/CAPLfunctionIso11783TCILOnCA.md) | Is called from the IL when a Command Address message is received. |
| [TCIL_OnChangedState](Functions/CAPLfunctionIso11783TCILOnChangedState.md) | Is called if the IL has changed its state. |
| [TCIL_OnError](Functions/CAPLfunctionIso11783TCILOnError.md) | Is called if an error has occurred. |
| [TCIL_OnRequest](Functions/CAPLfunctionIso11783TCILOnRequest.md) | Is called if a request (0xEA00) is received. |
| [TCIL_OnRxMessage](Functions/CAPLfunctionIso11783TCILOnRxMessage.md) | Is called from the IL if the IL receives the parameter group, namely **before** the parameter group is processed by the IL. |
| [TCIL_OnTxMessage](Functions/CAPLfunctionIso11783TCILOnTxMessage.md) | Is called if a message was sent successfully. |
| [TCIL_OnTxPrepare](Functions/CAPLfunctionIso11783TCILOnTxPrepare.md) | Is called before a parameter group is sent. |

#### DTC Support 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_ActivateDiagnosticsSupport](Functions/CAPLfunctionIso11783TCILActivateDiagnosticsSupport.md) | Activates or deactivates the support of ISO11783 diagnostics by the IL. |
| [TCIL_ActivateDTC](Functions/CAPLfunctionIso11783TCILActivateDTC.md) | Activates a diagnostics trouble code (DTC) and add it to the list of active DTCs. |
| [TCIL_ClearAllDTCs](Functions/CAPLfunctionIso11783TCILClearAllDTCs.md) | Clears the list of active DTCs as well as the list of previously active DTCs. |
| [TCIL_DeactivateDTC](Functions/CAPLfunctionIso11783TCILDeactivateDTC.md) | Deactivates a diagnostics trouble code (DTC) and removes it from the list of active DTCs. |
| [TCIL_GetDTCStatus](Functions/CAPLfunctionIso11783TCILGetDTCStatus.md) | Returns the current occurrence count of a diagnostics trouble code (DTC). |

#### Node Control 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_AcceptRxPG](Functions/CAPLfunctionIso11783TCILAcceptRxPG.md) | Checks if the received parameter group is addressed to the TC IL. |
| [TCIL_ControlInit](Functions/CAPLfunctionIso11783TCILControlInit.md) | Suppress the auto-start function of the IL. |
| [TCIL_ControlStart](Functions/CAPLfunctionIso11783TCILControlStart.md) | Activate node to start Address Claiming. |
| [TCIL_ControlStop](Functions/CAPLfunctionIso11783TCILControlStop.md) | Deactivates the IL and stops sending cyclic messages. |
| [TCIL_EnableAddressViolationDetection](Functions/CAPLfunctionIso11783TCILEnableAddressViolationDetection.md) | Activates detection of address violations by other nodes. |
| [TCIL_EnableNameManagement](Functions/CAPLfunctionIso11783TCILEnableNameManagement.md) | This function activates the name management of a node. |
| [TCIL_GetAddress](Functions/CAPLfunctionIso11783TCILGetAddress.md) | Returns the address that is used by the TC IL. |
| [TCIL_GetState](Functions/CAPLfunctionIso11783TCILGetState.md) | Returns the current state of the TC IL. |
| [TCIL_SetNodeProperty](Functions/CAPLfunctionIso11783TCILSetNodeProperty.md) | Changes an internal property of the node. |
| [TCIL_GetDeviceName](Functions/CAPLfunctionIso11783TCILGetDeviceName.md) | Gets the NAME as reported on the bus. |

#### Other Functions 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_GetLastError](Functions/CAPLfunctionIso11783TCILGetLastError.md) | Returns the value of the last called TC IL function. |
| [TCIL_GetLastErrorText](Functions/CAPLfunctionIso11783TCILGetLastErrorText.md) | Returns the textual description of the value of the last called TC IL function. |
| [TCIL_SetVerbosity](Functions/CAPLfunctionIso11783TCILSetVerbosity.md) | Set verbosity for writing in Write Window. |

#### Signal/Message Access 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_SetMsgEvent](Functions/CAPLfunctionIso11783TCILSetMsgEvent.md) | Sends a message immediately. |
| [TCIL_SetMsgRawData](Functions/CAPLfunctionIso11783TCILSetMsgRawData.md) | Sets the data bytes of the message. |
| [TCIL_SetSignal](Functions/CAPLfunctionIso11783TCILSetSignal.md) | Sets the physical value of a signal. |
| [TCIL_SetSignalRaw](Functions/CAPLfunctionIso11783TCILSetSignalRaw.md) | Sets the raw value of a signal. |

#### TC – Client Control 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_MeasurementCommandRaw](Functions/CAPLfunctionIso11783TCILMeasurementCommandRawPhysical.md) | Sends a trigger definition to the client (using the raw value). |
| [TCIL_MeasurementCommandPhysical](Functions/CAPLfunctionIso11783TCILMeasurementCommandRawPhysical.md) | Sends a trigger definition to the client (using the physical value). |
| [TCIL_RequestValueCommand](Functions/CAPLfunctionIso11783TCILRequestValueCommand.md) | Sends the **Request Value** command to the client. |
| [TCIL_RequestVersion](Functions/CAPLfunctionIso11783TCILRequestVersion.md) | Requests the **Version** message from the client. |
| [TCIL_StartTask](Functions/CAPLfunctionIso11783TCILStartTask.md) | Starts a task. |
| [TCIL_StopTask](Functions/CAPLfunctionIso11783TCILStopTask.md) | Stops a task. |
| [TCIL_ValueAndAckCommand](Functions/CAPLfunctionIso11783TCILValueAndAckCommandRawPhysical.md) | Sends the current value of a data entity to the client with **Set Value and Acknowledge command**. |
| [TCIL_ValueAndAckCommandRaw](Functions/CAPLfunctionIso11783TCILValueAndAckCommandRawPhysical.md) | Sets the value of a data entity (using the raw value) and sends the value to the client with **Set Value and Acknowledge command**. |
| [TCIL_ValueAndAckCommandPhysical](Functions/CAPLfunctionIso11783TCILValueAndAckCommandRawPhysical.md) | Sets the value of a data entity (using the physical value) and sends the value to the client with **Set Value and Acknowledge command**. |
| [TCIL_ValueCommand](Functions/CAPLfunctionIso11783TCILValueCommandRawPhysical.md) | Sends the current value of a data entity to the client with **Value command**. |
| [TCIL_ValueCommandRaw](Functions/CAPLfunctionIso11783TCILValueCommandRawPhysical.md) | Sets the value of a data entity (using the raw value) and sends the value to the client with **Value command**. |
| [TCIL_ValueCommandPhysical](Functions/CAPLfunctionIso11783TCILValueCommandRawPhysical.md) | Sets the value of a data entity (using the physical value) and sends the value to the client with **Value command**. |

#### TC – Fault Injection for Messages 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_BlockRxMessage](Functions/CAPLfunctionIso11783TCILBlockRxMessage.md) | Prevents processing of a received message by the Interaction Layer. |
| [TCIL_ResetBlockedRxMessage](Functions/CAPLfunctionIso11783TCILResetBlockedRxMessage.md) |  |
| [TCIL_ResetAllBlockedRxMessages](Functions/CAPLfunctionIso11783TCILResetAllBlockedRxMessages.md) |  |
| [TCIL_BlockTxMessage](Functions/CAPLfunctionIso11783TCILBlockRxMessage.md) | Prevents transmitting of a message generated by the interaction layer. |
| [TCIL_ResetBlockedTxMessage](Functions/CAPLfunctionIso11783TCILResetBlockedTxMessage.md) |  |
| [TCIL_ResetAllBlockedTxMessages](Functions/CAPLfunctionIso11783TCILResetAllBlockedTxMessages.md) |  |
| [TCIL_DelayRxMessage](Functions/CAPLfunctionIso11783TCILDelayRxMessage.md) | Delays processing of a received message by the interaction layer. |
| [TCIL_ResetDelayedRxMessage](Functions/CAPLfunctionIso11783TCILResetDelayedRxMessage.md) |  |
| [TCIL_ResetAllDelayedRxMessage](Functions/CAPLfunctionIso11783TCILResetAllDelayedRxMessage.md) |  |
| [TCIL_ManipulateMessage](Functions/CAPLfunctionIso11783TCILManipulateMessage.md) | Modifies the content of a message generated and sent by the interaction layer. |
| [TCIL_ResetManipulatedMessage](Functions/CAPLfunctionIso11783TCILResetManipulatedMessage.md) |  |
| [TCIL_ResetAllManipulatedMessages](Functions/CAPLfunctionIso11783TCILResetAllManipulatedMessages.md) |  |
| [TCIL_SetResponseContent](Functions/CAPLfunctionIso11783TCILSetResponseContent.md) | Changes the content of the next TC response. |
| [TCIL_ResetResponseContent](Functions/CAPLfunctionIso11783TCILResetResponseContent.md) |  |
| [TCIL_SetTCStatus](Functions/CAPLfunctionIso11783TCILSetTCStatus.md) | Changes the content and cycle time of the TC Status message. |
| [TCIL_ResetTCStatus](Functions/CAPLfunctionIso11783TCILResetTCStatus.md) |  |

#### TC – Fault Injection for Transport Protocols 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_BlockTxTpAbort](Functions/CAPLfunctionIso11783TCILBlockTxTpAbort.md) | Prevents transmission of (E)TP.Abort message by the Interaction Layer. |
| [TCIL_ResetBlockedTxTpAbort](Functions/CAPLfunctionIso11783TCILResetBlockedTxTpAbort.md) |  |
| [TCIL_BlockTxTpCts](Functions/CAPLfunctionIso11783TCILBlockTxTpCts.md) | Prevents transmission of (E)TP.CTS message by the Interaction Layer. |
| [TCIL_ResetBlockedTxTpCts](Functions/CAPLfunctionIso11783TCILResetBlockedTxTpCts.md) |  |
| [TCIL_BlockTxTpDpo](Functions/CAPLfunctionIso11783TCILBlockTxTpDpo.md) | Prevents transmitting of a ETP.DPO message generated and sent by the interaction layer. |
| [TCIL_ResetBlockedTxTpDpo](Functions/CAPLfunctionIso11783TCILResetBlockedTxTpDpo.md) |  |
| [TCIL_BlockTxTpDt](Functions/CAPLfunctionIso11783TCILBlockTxTpDt.md) | Prevents transmission of (E)TP.DT message by the Interaction Layer. |
| [TCIL_ResetBlockedTxTpDt](Functions/CAPLfunctionIso11783TCILResetBlockedTxTpDt.md) |  |
| [TCIL_BlockTxTpEoma](Functions/CAPLfunctionIso11783TCILBlockTxTpEoma.md) | Prevents transmission of (E)TP.EoMA message by the Interaction Layer. |
| [TCIL_ResetBlockedTxTpEoma](Functions/CAPLfunctionIso11783TCILResetBlockedTxTpEoma.md) |  |
| [TCIL_DelayTxTpAbort](Functions/CAPLfunctionIso11783TCILDelayTxTpAbort.md) | Delays transmission of (E)TP.Abort message by the Interaction Layer. |
| [TCIL_ResetDelayededTxTpAbort](Functions/CAPLfunctionIso11783TCILResetDelayededTxTpAbort.md) |  |
| [TCIL_DelayTxTpCts](Functions/CAPLfunctionIso11783TCILDelayTxTpCts.md) | Delays transmission of (E)TP.CTS message by the Interaction Layer. |
| [TCIL_ResetDelayedTxTpCts](Functions/CAPLfunctionIso11783TCILResetDelayedTxTpCts.md) |  |
| [TCIL_DelayTxTpDpo](Functions/CAPLfunctionIso11783TCILDelayTxTpDpo.md) | Delays transmitting of a ETP.DPO message generated and sent by the interaction layer. |
| [TCIL_ResetDelayedTxTpDpo](Functions/CAPLfunctionIso11783TCILResetDelayedTxTpDpo.md) |  |
| [TCIL_DelayTxTpDt](Functions/CAPLfunctionIso11783TCILDelayTxTpDt.md) | Delays transmission of (E)TP.DT message by the Interaction Layer. |
| [TCIL_ResetDelayedTxTpDt](Functions/CAPLfunctionIso11783TCILResetDelayedTxTpDt.md) |  |
| [TCIL_DelayTxTpEoma](Functions/CAPLfunctionIso11783TCILDelayTxTpEoma.md) | Delays transmission of (E)TP.EoMA message by the Interaction Layer. |
| [TCIL_ResetDelayedTxTpEoma](Functions/CAPLfunctionIso11783TCILResetDelayedTxTpEoma.md) |  |
| [TCIL_FreezeTp](Functions/CAPLfunctionIso11783TCILFreezeTp.md) | Freezes the current (E)TP connection immediately. |
| [TCIL_UnfreezeTp](Functions/CAPLfunctionIso11783TCILUnfreezeTp.md) |  |
| [TCIL_KillTp](Functions/CAPLfunctionIso11783TCILKillTp.md) |  |

#### TC – Other Functions 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_ConnectSysVarWithDataEntity](Functions/CAPLfunctionIso11783TCILConnectSysVarWithDataEntity.md) | Connects a data entity to a system variable. |
| [TCIL_ConnectSysVarWithSection](Functions/CAPLfunctionIso11783TCILConnectSysVarWithSection.md) | Connects a single section state to a system variable. |
| [TCIL_ExportAllDdops](Functions/CAPLfunctionIso11783TCILExportAllDdops.md) | Exports the device descriptor object pools of all Task Controller clients into a file. |
| [TCIL_ExportDdop](Functions/CAPLfunctionIso11783TCILExportDdop.md) | Exports the device descriptor object pool into a file. |
| [TCIL_GetDesignator](Functions/CAPLfunctionIso11783TCILGetDesignator.md) | Returns the designator of DeviceProcessData (DPD) or DeviceProperty (DPT). |
| [TCIL_GetDeviceParameters](Functions/CAPLfunctionIso11783TCILGetDeviceParameters.md) | Returns parameters of the client device which are contained in the Device XML element (DVC) of the device description. |
| [TCIL_GetElementNumbers](Functions/CAPLfunctionIso11783TCILGetElementNumbers.md) | Returns a list of corresponding element numbers for the given DDI. |
| [TCIL_GetValuePresentationData](Functions/CAPLfunctionIso11783TCILGetValuePresentationData.md) | Returns all properties (id, offset, scale, numberDecimals, unitDesignator) of the ValuePresentation object. |
| [TCIL_MakeDdopAvailable](Functions/CAPLfunctionIso11783TCILMakeDdopAvailable.md) | Enables a device descriptor object pool (DDOP) to be loaded by Object-pool Activate message. |
| [TCIL_RemoveAllDdops](Functions/CAPLfunctionIso11783TCILRemoveAllDdops.md) | Removes the device descriptor object pools of all Task Controller clients. |

#### TC – Peer Control 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_AssignReceiver](Functions/CAPLfunctionIso11783TCILAssignReceiver.md) | Sends an **Assign Receiver** message to the **setpoint value user** device. |
| [TCIL_AssignTransmitter](Functions/CAPLfunctionIso11783TCILAssignTransmitter.md) | Sends an **Assign Transmitter** message to the **setpoint value source** device. |
| [TCIL_CreatePeerControlAssignment](Functions/CAPLfunctionIso11783TCILCreatePeerControlAssignment.md) | Creates an assignment of a settable process data object to a setpoint value source. |
| [TCIL_RemovePeerControlAssignment](Functions/CAPLfunctionIso11783TCILRemovePeerControlAssignment.md) | Removes an assignment of a settable process data object to a setpoint value source. |
| [TCIL_UnassignReceiver](Functions/CAPLfunctionIso11783TCILUnassignReceiver.md) | Sends an **Unassign Receiver** message to the **setpoint value user** device. |
| [TCIL_UnassignTransmitter](Functions/CAPLfunctionIso11783TCILUnassignTransmitter.md) | Sends an **Unassign Transmitter** message to the **setpoint value source** device. |

#### TC – Value Access 

| Functions | Short Description |
|-----------|-------------------|
| [TCIL_GetSectionState](Functions/CAPLfunctionIso11783TCILGetSectionState.md) | Returns the current state of a single section. |
| [TCIL_GetValueRaw](Functions/CAPLfunctionIso11783TCILGetValueRawPhysical.md) | Returns the current raw value of a data entity. |
| [TCIL_GetValuePhysical](Functions/CAPLfunctionIso11783TCILGetValueRawPhysical.md) | Returns the current physical value of a data entity. |
| [TCIL_SetSectionState](Functions/CAPLfunctionIso11783TCILSetSectionState.md) | Sets the state of a single section without sending any command. |
| [TCIL_SetValueRaw](Functions/CAPLfunctionIso11783TCILSetValueRawPhysical.md) | Sets the value of a data entity without sending any command (using the raw value). |
| [TCIL_SetValuePhysical](Functions/CAPLfunctionIso11783TCILSetValueRawPhysical.md) | Sets the value of a data entity without sending any command (using the physical value). |

[IL Error Codes](../../CAPLfunctionsISOj1939ErrorCodes.md) • [TC IL Functional Properties](CAPLfunctionsISOILTCProperties.md) • [TC IL Network Properties](CAPLfunctionsISOILTCNetworkProperties.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
