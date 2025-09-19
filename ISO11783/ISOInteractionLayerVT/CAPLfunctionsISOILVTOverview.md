[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/CAPLfunctionsISOILVTOverview.md)

**CAPL Functions** » [ISO11783](../CAPLfunctionsISO11783Overview.md) » Virtual Terminal Interaction Layer (VT IL)

# ISO11783 Virtual Terminal Interaction Layer
*(Only available with ISO11783!)*

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

To use the CAPL functions the **ISO11783_VT_IL.dll** i.e. [Virtual Terminal Interaction Layer (VT IL)](../../../Shared/ISO11783/ISO11783ILVT.md) must be included.

**ON THIS PAGE:**

- [Callback Functions](#Callback)
- [DTC Support](#DiagnosticFunctions)
- [Node Control](#Node)
- [Other Functions](#Other)
- [Signal/Message Access](#Signal/M)
- [VT - Fault Injection for Messages](#VTFaultInjection)
- [VT - Fault Injection for Transport Protocols](#VTFaultInjectionTP)
- [VT - Handling](#VTHandling)
- [VT - Handling (User-Layout Mask)](#VTHandlingUserLayoutMask)
- [VT - Other Functions](#VTOtherFunctions)
- [VT - Value Request](#VTValueRequest)

## Callback Functions

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_OnAddressClaimConflict](Functions/CAPLfunctionIso11783VTILOnAddressClaimConflict.md) | Is called if an address conflict is detected. |
| [VTIL_OnAddressViolation](Functions/CAPLfunctionIso11783VTILOnAddressViolation.md) | Is called if an address violation is detected. |
| [VTIL_OnCA](Functions/CAPLfunctionIso11783VTILOnCA.md) | Is called from the IL when a Command Address message is received. |
| [VTIL_OnChangedState](Functions/CAPLfunctionIso11783VTILOnChangedState.md) | Is called if the IL has changed its state. |
| [VTIL_OnError](Functions/CAPLfunctionIso11783VTILOnError.md) | Is called if an error has occurred. |
| [VTIL_OnRequest](Functions/CAPLfunctionIso11783VTILOnRequest.md) | Is called if a request (0xEA00) is received. |
| [VTIL_OnRxMessage](Functions/CAPLfunctionIso11783VTILOnRxMessage.md) | Is called from the IL if the IL receives the parameter group, namely **before** the parameter group is processed by the IL. |
| [VTIL_OnTxMessage](Functions/CAPLfunctionIso11783VTILOnTxMessage.md) | Is called if a message was sent successfully. |
| [VTIL_OnTxPrepare](Functions/CAPLfunctionIso11783VTILOnTxPrepare.md) | Is called before a parameter group is sent. |

## DTC Support

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_ActivateDiagnosticsSupport](Functions/CAPLfunctionIso11783VTILActivateDiagnosticsSupport.md) | Activates or deactivates the support of ISO11783 diagnostics by the IL. |
| [VTIL_ActivateDTC](Functions/CAPLfunctionIso11783VTILActivateDTC.md) | Activates a diagnostics trouble code (DTC) and add it to the list of active DTCs. |
| [VTIL_ClearAllDTCs](Functions/CAPLfunctionIso11783VTILClearAllDTCs.md) | Clears the list of active DTCs as well as the list of previously active DTCs. |
| [VTIL_DeactivateDTC](Functions/CAPLfunctionIso11783VTILDeactivateDTC.md) | Deactivates a diagnostics trouble code (DTC) and removes it from the list of active DTCs. |
| [VTIL_GetDTCStatus](Functions/CAPLfunctionIso11783VTILGetDTCStatus.md) | Returns the current occurrence count of a diagnostics trouble code (DTC). |

## Node Control

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_AcceptRxPG](Functions/CAPLfunctionIso11783VTILAcceptRxPG.md) | Checks if the received parameter group is addressed to the ISO11783 IL. |
| [VTIL_ControlInit](Functions/CAPLfunctionIso11783VTILControlInit.md) | Suppress the auto-start function of the IL. |
| [VTIL_ControlStart](Functions/CAPLfunctionIso11783VTILControlStart.md) | Activate node to start Address Claiming. |
| [VTIL_ControlStop](Functions/CAPLfunctionIso11783VTILControlStop.md) | Deactivates the IL and stops sending cyclic messages. |
| [VTIL_EnableAddressViolationDetection](Functions/CAPLfunctionIso11783VTILEnableAddressViolationDetection.md) | Activates detection of address violations by other nodes. |
| [VTIL_EnableNameManagement](Functions/CAPLfunctionIso11783VTILEnableNameManagement.md) | This function activates the name management of a node. |
| [VTIL_GetAddress](Functions/CAPLfunctionIso11783VTILGetAddress.md) | Returns the address that is used by the VT IL. |
| [VTIL_GetState](Functions/CAPLfunctionIso11783VTILGetState.md) | Returns the current state of the VT IL. |
| [VTIL_SetNodeProperty](Functions/CAPLfunctionIso11783VTILSetNodeProperty.md) | Changes an internal property of the node. |
| [VTIL_GetDeviceName](Functions/CAPLfunctionIso11783VTILGetDeviceName.md) | Gets the NAME as reported on the bus. |

## Other Functions

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_GetLastError](Functions/CAPLfunctionIso11783VTILGetLastError.md) | Returns the value of the last called VT IL function. |
| [VTIL_GetLastErrorText](Functions/CAPLfunctionIso11783VTILGetLastErrorText.md) | Returns the textual description of the value of the last called VT IL function. |
| [VTIL_SetVerbosity](Functions/CAPLfunctionIso11783VTILSetVerbosity.md) | Set verbosity for writing in Write Window. |

## Signal/Message Access

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_SetMsgEvent](Functions/CAPLfunctionIso11783VTILSetMsgEvent.md) | Sends a message immediately. |
| [VTIL_SetMsgRawData](Functions/CAPLfunctionIso11783VTILSetMsgRawData.md) | Sets the data bytes of the message. |
| [VTIL_SetSignal](Functions/CAPLfunctionIso11783VTILSetSignal.md) | Sets the physical value of a signal. |
| [VTIL_SetSignalRaw](Functions/CAPLfunctionIso11783VTILSetSignalRaw.md) | Sets the raw value of a signal. |

## VT – Fault Injection for Messages

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_BlockRxMessage](Functions/CAPLfunctionIso11783VTILBlockRxMessage.md) | Prevents processing of a received message by the Interaction Layer. |
| [VTIL_BlockTxMessage](Functions/CAPLfunctionIso11783VTILBlockTxMessage.md) | Prevents transmitting of a message generated by the interaction layer. |
| [VTIL_DelayRxMessage](Functions/CAPLfunctionIso11783VTILDelayRxMessage.md) | Delays processing of a received message by the interaction layer. |
| [VTIL_ManipulateMessage](Functions/CAPLfunctionIso11783VTILManipulateMessage.md) | Modifies the content of a message generated and sent by the interaction layer. |
| [VTIL_SetResponseContent](Functions/CAPLfunctionIso11783VTILSetResponseContent.md) | Changes the content of the next VT response. |
| [VTIL_SetVTStatus](Functions/CAPLfunctionIso11783VTILSetVTStatus.md) | Changes the content and cycle time of the VT Status message. |

## VT – Fault Injection for Transport Protocols

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_BlockTxTpAbort](Functions/CAPLfunctionIso11783VTILBlockTxTpAbort.md) | Prevents transmission of (E)TP.Abort message by the Interaction Layer. |
| [VTIL_BlockTxTpCts](Functions/CAPLfunctionIso11783VTILBlockTxTpCts.md) | Prevents transmission of (E)TP.CTS message by the Interaction Layer. |
| [VTIL_BlockTxTpDpo](Functions/CAPLfunctionIso11783VTILBlockTxTpDpo.md) | Prevents transmitting of a ETP.DPO message generated and sent by the interaction layer. |
| [VTIL_BlockTxTpDt](Functions/CAPLfunctionIso11783VTILBlockTxTpDt.md) | Prevents transmission of (E)TP.DT message by the Interaction Layer. |
| [VTIL_BlockTxTpEoma](Functions/CAPLfunctionIso11783VTILBlockTxTpEoma.md) | Prevents transmission of (E)TP.EoMA message by the Interaction Layer. |
| [VTIL_DelayTxTpAbort](Functions/CAPLfunctionIso11783VTILDelayTxTpAbort.md) | Delays transmission of (E)TP.Abort message by the Interaction Layer. |
| [VTIL_DelayTxTpCts](Functions/CAPLfunctionIso11783VTILDelayTxTpCts.md) | Delays transmission of (E)TP.CTS message by the Interaction Layer. |
| [VTIL_DelayTxTpDpo](Functions/CAPLfunctionIso11783VTILDelayTxTpDpo.md) | Delays transmitting of a ETP.DPO message generated and sent by the interaction layer. |
| [VTIL_DelayTxTpDt](Functions/CAPLfunctionIso11783VTILDelayTxTpDt.md) | Delays transmission of (E)TP.DT message by the Interaction Layer. |
| [VTIL_DelayTxTpEoma](Functions/CAPLfunctionIso11783VTILDelayTxTpEoma.md) | Delays transmission of (E)TP.EoMA message by the Interaction Layer. |
| [VTIL_FreezeTp](Functions/CAPLfunctionIso11783VTILFreezeTp.md) | Freezes the current (E)TP connection immediately. |

## VT – Handling

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_ACK, VTIL_ACKMsg](Functions/CAPLfunctionIso11783VTILACKmsg.md) | Simulates pressing of the ACK means of the Virtual Terminal. |
| [VTIL_ActivateWorkingSet](Functions/CAPLfunctionIso11783VTILActivateWorkingSet.md) | Simulates the activating of a Working Set in the Virtual Terminal. |
| [VTIL_AddKeyGroup](Functions/CAPLfunctionIso11783VTILAddKeyGroup.md) | Adds a Key Group to a User-Layout Data Mask of the Virtual Terminal. |
| [VTIL_AddWindowMask](Functions/CAPLfunctionIso11783VTILAddWindowMask.md) | Adds a Window Mask to a User-Layout Data Mask of the Virtual Terminal. |
| [VTIL_ClearUserLayoutMask](Functions/CAPLfunctionIso11783VTILClearUserLayoutMask.md) | Removes all Window Masks and all Key Groups from a User-Layout Mask of the Virtual Terminal. |
| [VTIL_CreateAuxAssignment](Functions/CAPLfunctionIso11783VTILCreateAuxAssignment.md) | Assigns an Auxiliary Input to an Auxiliary Function |
| [VTIL_EditNumericValue](Functions/CAPLfunctionIso11783VTILEditNumericValue.md) | Simulates editing of an Input Number or Input List object. |
| [VTIL_EditStringValue](Functions/CAPLfunctionIso11783VTILEditStringValue.md) | Simulates editing of an Input String object. |
| [VTIL_ESC, VTIL_ESCMsg](Functions/CAPLfunctionIso11783VTILESC.md) | Simulates pressing of the ESC means of the Virtual Terminal. |
| [VTIL_PressButton](Functions/CAPLfunctionIso11783VTILPressButton.md) | Simulates pressing of a Button of the active Data/Alarm Mask. |
| [VTIL_PressSoftKey](Functions/CAPLfunctionIso11783VTILPressSoftKey.md) | Simulates pressing of a Soft Key of the active Soft Key Mask. |
| [VTIL_RemoveAuxAssignment](Functions/CAPLfunctionIso11783VTILRemoveAuxAssignment.md) | Removes an auxiliary assignment |
| [VTIL_RemoveKeyGroup](Functions/CAPLfunctionIso11783VTILRemoveKeyGroup.md) | Removes a Key Group from a User-Layout Soft Key Mask of the Virtual Terminal. |
| [VTIL_RemoveWindowMask](Functions/CAPLfunctionIso11783VTILRemoveWindowMask.md) | Removes a Window Mask from a User-Layout Data Mask of the Virtual Terminal. |
| [VTIL_SelectInputObject](Functions/CAPLfunctionIso11783VTILSelectInputObject.md) | Sends the VT Select Input Object message. |
| [VTIL_Touch](Functions/CAPLfunctionIso11783VTILTouch.md) | Simulates touching into the Data Mask. |

## VT – Handling (User-Layout Mask)

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_AddKeyGroup](Functions/CAPLfunctionIso11783VTILAddKeyGroup.md) | Adds a Key Group to a User-Layout Data Mask of the Virtual Terminal. |
| [VTIL_AddWindowMask](Functions/CAPLfunctionIso11783VTILAddWindowMask.md) | Adds a Window Mask to a User-Layout Data Mask of the Virtual Terminal. |
| [VTIL_ClearUserLayoutMask](Functions/CAPLfunctionIso11783VTILClearUserLayoutMask.md) | Removes all Window Masks and all Key Groups from a User-Layout Mask of the Virtual Terminal. |
| [VTIL_RemoveKeyGroup](Functions/CAPLfunctionIso11783VTILRemoveKeyGroup.md) | Removes a Key Group from a User-Layout Soft Key Mask of the Virtual Terminal. |
| [VTIL_RemoveWindowMask](Functions/CAPLfunctionIso11783VTILRemoveWindowMask.md) | Removes a Window Mask from a User-Layout Data Mask of the Virtual Terminal. |

## VT – Other Functions

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_ConnectSysVar](Functions/CAPLfunctionIso11783VTILConnectSysVar.md) | Connects an object from the object pool to a system variable. |
| [VTIL_DeleteAllStoredVersions](Functions/CAPLfunctionIso11783VTILDeleteAllStoredVersions.md) | Deletes all stored object pool versions. |
| [VTIL_ExportObjectPool](Functions/CAPLfunctionIso11783VTILExportObjectPool.md) | Exports the current object pool of the Working Set Master into a file (iop). |
| [VTIL_GetChildObjectId](Functions/CAPLfunctionIso11783VTILGetChildObjectId.md) | Returns the ID of a child object. |
| [VTIL_GetIdOfVisibleObject](Functions/CAPLfunctionIso11783VTILGetIdOfVisibleObject.md) | Returns the object ID of a visible object at a specified position. |
| [VTIL_GetNextTAN](Functions/CAPLfunctionIso11783VTILGetNextTAN.md) | Gets the TAN that will be used in the next activation message. |
| [VTIL_GetNumberOfChildObjects](Functions/CAPLfunctionIso11783VTILGetNumberOfChildObjects.md) | Returns the number of child objects contained in an object. |
| [VTIL_IsObjectVisible](Functions/CAPLfunctionIso11783VTILIsObjectVisible.md) | Checks if an object is visible in the current **Data Mask** or **Soft Key Mask**. |
| [VTIL_PressISB](Functions/CAPLfunctionIso11783VTILPressISB.md) | Simulates pressing the ISOBUS Shortcut Button **[ISB]** of the Virtual Terminal. |
| [VTIL_RegisterObjectPool](Functions/CAPLfunctionIso11783VTILRegisterObjectPool.md) | Registers an object pool file (iop). |
| [VTIL_SaveAsImage](Functions/CAPLfunctionIso11783VTILSaveAsImage.md) | Saves the current Data/Alarm Mask or one of the current Soft Keys as an image. |
| [VTIL_SetNextTAN](Functions/CAPLfunctionIso11783VTILSetNextTAN.md) | Sets the TAN to be used in the next activation message. |

## VT – Value Request

| Functions | Short Description |
|-----------|-------------------|
| [VTIL_GetActiveMask](Functions/CAPLfunctionIso11783VTILGetActiveMask.md) | Returns object ID of the active Data or Alarm Mask. |
| [VTIL_GetDisplayedValue](Functions/CAPLfunctionIso11783VTILGetDisplayedValue.md) | Returns the displayed value of an object. |
| [VTIL_GetDwordValue](Functions/CAPLfunctionIso11783VTILGetDwordValue.md) | Returns the value of an object attribute. |
| [VTIL_GetDoubleValue](Functions/CAPLfunctionIso11783VTILGetDwordValue.md) | Returns the value of an object or of an object attribute. |
| [VTIL_GetStringValue](Functions/CAPLfunctionIso11783VTILGetDwordValue.md) | Returns the value of an object. |

[IL Error Codes](../../CAPLfunctionsISOj1939ErrorCodes.md) • [VT IL Properties](CAPLfunctionsISOILVTProperties.md) • [VT IL Network Properties](CAPLfunctionsISOILVTNetworkProperties.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
