[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CAPLFunctionsSmartChargingOverview.md)

## SmartCharging CAPL Functions

[CAPL Functions](../CAPLfunctions.md) » SmartCharging CAPL Functions

**Valid for**: CANoe DE • CANoe4SW DE

- **SmartCharging**
  - Only available with Option SmartCharging.
  - The available CAPL functions depend on the protocol(s) used and thus the underlying technology.
  - **CCS (Communication Setup)**
    - CCS is used for the following protocol: ISO15118-20.
    - Only available if the CCS-Binding is activated.
    - To use these CAPL-Functions, CCS-Binding needs to be activated in the [Communication Setup](../../CANoeCANalyzer/Windows/CommunicationSetup/CommunicationSetup.md) window.
  - **CHAdeMO (Communication Setup)**
    - CHAdeMO is used for the following protocol: CHAdeMO.
    - To use these CAPL-Functions, CHAdeMO-Binding needs to be activated in the [Communication Setup](../../CANoeCANalyzer/Windows/CommunicationSetup/CommunicationSetup.md) window.
  - **SCC Modeling Libraries (Simulation Setup)**
    - The modeling libraries are used for the following protocols: DIN70121, ISO 15118-2.
    - To use the CAPL functions, the modeling library **SCC_Vehicle.vmodule** and/or **SCC_ChargePoint.vmodule** must be included.
    - All response callbacks with **ResponseCode** parameter contain a Boolean parameter in their signatures that specifies the type of response code.
  - **GB/T 27930 Modeling Libraries (Simulation Setup)**
    - The modeling libraries are used for the following protocol: GB/T 27930.
    - To use the CAPL functions, the modeling library [GBT27930_IL.vmodule](../../CANoeCANalyzer/ISO11783/procedures/UseNodelayerDLL.md) must be included. Refer to the help page [GB/T 27930 Interaction Layer](../../Shared/ISO11783/J1939GBT27930IL.md).
  - **OCPP (Communication Setup)**
    - OCPP is used for the following protocol: OCPP.
    - To use these CAPL-Functions, OCPP-Binding needs to be activated in the [Communication Setup](../../CANoeCANalyzer/Windows/CommunicationSetup/CommunicationSetup.md) window.

**Note:** You cannot mix CCS Binding CAPL functions with SCC Modeling Library CAPL functions as they address different protocols.

### CCS (Communication Setup)

#### Callback Functions

- **Shared Callback Functions**
  - [InvalidMessageReceivedInd](Callbacks/CAPLfunctionSCCInvalidMessageReceivedInd.md): The callback is called when a SDP or V2G message is received with an invalid format and is therefore not further processed.
  - [OnGenericVSHostActionInd](Callbacks/CAPLfunctionSCCOnGenericVSHostActionInd.md): The callback is called as soon as a VS_Host_Action.Ind or equivalent message is received.
  - [OnLastReceivedMessageIdChanged](CCSBindingCallbacks/CAPLfunctionOnLastReceivedMessageIdChanged.md): Indication that is triggered whenever a message was received.
  - [OnLastTransmittedMessageIdChanged](CCSBindingCallbacks/CAPLfunctionOnLastTransmittedMessageIdChanged.md): Indication that is triggered whenever a message was transmitted.
  - [OnPreSendMessageIdChanged](Callbacks/CAPLfunctionSCCOnPreSendMessageIdChanged.md): Indication that a message will be sent.
  - [OnSocketReceivedInd](Callbacks/CAPLfunctionSCCOnSocketReceivedInd.md): Indication that is triggered when a TCP/UDP packet containing a Vehicle2Grid or SECC Discovery message is received.
  - [PayloadPreSendInd](Callbacks/CAPLfunctionCCSPayloadPreSendInd.md): Indication that is triggered before a TCP/UDP packet containing a Vehicle2Grid or SECC Discovery message is sent.
  - [SLACFinishedInd](CCSBindingFunctions/CAPLfunctionSLACFinishedInd.md): Indication that is triggered when the SLACFinished value changes.
  - [TransportLayerConnectInd](CCSBindingFunctions/CAPLfunctionTransportLayerConnectInd.md): Indication that is triggered when the TransportLayer is connected.
  - [TransportLayerDisconnectInd](CCSBindingFunctions/CAPLfunctionTransportLayerDisconnectInd.md): Indication that is triggered when the TransportLayer is disconnected.

#### General Functions

- **Shared Functions**
  - [StartSimulation](CCSBindingFunctions/CAPLfunctionStartSimulation.md): Starts the simulation of the DO.
  - [StopSimulation](CCSBindingFunctions/CAPLfunctionStopSimulation.md): Stops the simulation of the DO.
  - [ResetSimulation](CCSBindingFunctions/CAPLfunctionResetSimulation.md): Resets the DO.
  - [SetAdHocSendingEnabled](CCSBindingFunctions/CAPLfunctionSetAdHocSendingEnabled.md): Enabled manual sending of messages.
  - [SetSchema](CCSBindingFunctions/CAPLfunctionSetSchema.md): Sets the schema used for decoding and encoding.
  - [EnableAutoBodyFill](CCSBindingFunctions/CAPLfunctionEnableAutoBodyFill.md): (De-)Activates automatic population of message bodies with data. (Default: Active)
  - [EnableAutoHeaderFill](CCSBindingFunctions/CAPLfunctionEnableAutoHeaderFill.md): (De-)Activates automatic population of message headers with data. (Default: Active)
  - [TCPShutdown](CCSBindingFunctions/CAPLfunctionTCPShutdown.md): Triggers a closing of the TCP connection.
  - [GetEthernetSettings](CCSBindingFunctions/CAPLfunctionGetEthernetSettings.md): Gets the MAC and IPv6 address of the DO.
  - [FinishProcessing](CCSBindingFunctions/CAPLfunctionFinishProcessing.md): Finishes the current **Ongoing** loop with **Finished**.
  - [SetFaultInjection](CCSBindingFunctions/CAPLfunctionSetFaultInjection.md): Enables fault injection within the V2G communication.
  - [SetHostMACAddress](CCSBindingFunctions/CAPLfunctionSetHostMACAddress.md): Sets the destination mac address for simulated PLC chip messages.

- **EV Functions**
  - [EnterChargingSessionPauseOrStandby](CCSBindingFunctions/CAPLfunctionEnterChargingSessionPauseOrStandby.md): Instructs the EV to enter the Charging Session **Pause** or **Standby** procedure, based on the attribute configuration.
  - [ExitStandby](CCSBindingFunctions/CAPLfunctionExitStandby.md): Instructs the EV to exit the standby procedure.
  - [ResetMessageTimeouts](CCSBindingFunctions/CAPLfunctionResetMessageTimeouts.md): Reset all message timeouts to their respective defaults.
  - [SetMessageTimeout](CCSBindingFunctions/CAPLfunctionSetMessageTimeout.md): Overwrites the timeout the StateMachine will check against for the specified message.
  - [StartScheduleRenegotiation](CCSBindingFunctions/CAPLfunctionStartScheduleRenegotiation.md): Manually start the ScheduleRenegotiation process on EV side.
  - [StopChargeLoop](CCSBindingFunctions/CAPLfunctionStopChargeLoop.md): Manually end the ChargeLoop on EV side.

- **EVSE Functions**
  - [SetNextEVSENotification](CCSBindingFunctions/CAPLfunctionSetNextEVSENotification.md): Overwrites the next **EVSENotification** sent in a response message.
  - [SetNextResponseCode](CCSBindingFunctions/CAPLfunctionISO20SetNextResponseCode.md): Overwrites the next **ResponseCode sent** in a response message.
  - [SLACGenerateNID](CCSBindingFunctions/CAPLfunctionSCCSLACGenerateNID.md): Generates a matching NID for a given NMK.
  - [SLACGenerateApplyKey](CCSBindingFunctions/CAPLfunctionSLACGenerateApplyKey.md): Generates a new NMK and NID pair and sends it to the chip.

### CHAdeMO (Communication Setup)

#### General Functions

- **Shared Functions**
  - StartSimulation: Starts the simulation of the DO.
  - ResetSimulation: Resets all internal data to their initial defaults (as at the start of measurement).
  - StartCyclicSending: Starts cyclic sending of all messages.
  - StopCyclicSending: Stops the sending of the cyclic messages. Can only be used if `StartCyclicSending` has been called before.
  - SetCyclicMessageDelay(uint8 milliseconds): Changes the message interval at which the messages are sent. Will be reset to default of 100[ms] using function `ResetSimulation`.

- **EV Functions**
  - SetMaximumChargingTime(uint32 seconds): Overwrites the calculated charging time of the vehicle

### Data Members

EV and EVSE contain data members that are either used by both sides or are only relevant for one side of the communication. They are used to pass internal states to the outside (consumed) or signals and measurement data to the inside (provided). Further information can be found on the page [Distributed Objects](../../CANoeCANalyzer/CommunicationConcept/CCDistributedObjects.md).

- **Shared Usage**
  - MeasVoltageCC1: consumed, double, —, Measured voltage on DP2.
  - MeasVoltageCC2: consumed, double, —, Measured voltage on DP3.
  - MeasVoltageCP: consumed, double, —, Measured voltage on Charge Sequence Signal1.
  - MeasVoltageCP2: consumed, double, —, Measured voltage on Charge Sequence Signal2.
  - MeasVoltageCP3: consumed, double, —, Measured voltage on Vehicle Charge Permission.
  - MeasVoltageCS: consumed, double, —, Measured voltage on Connector Proximity Detection.
  - SpecificationState: consumed, enum, State_A, The current state of the StateMachine. Possible values: State_A (0), State_B (1), State_C (2), State_D (3), State_E (4), State_F (5), State_G (6), State_H (7), State_I (8).

- **EV Specific**
  - ID100: provided, struct, —, CAN message H’100 (to be) sent by the vehicle, see Message_ID100_Type for details.
  - ID101: provided, struct, —, CAN message H’101 (to be) sent by the vehicle, see Message_ID101_Type for details.
  - ID102: provided, struct, —, CAN message H’102 (to be) sent by the vehicle, see Message_ID102_Type for details.
  - ID108: consumed, struct, —, CAN message H’108 (to be) received from the charger, see Message_ID108_Type for details.
  - ID109: consumed, struct, —, CAN message H’109 (to be) received from the charger, see Message_ID109_Type for details.

- **EVSE Specific**
  - S0: consumed, enum, open, Switch for U1. Possible values: open (0), close (1)
  - S1: consumed, enum, open, Switch for R1‘. Possible values: open (0), close (1)
  - d1: consumed, enum, open, Switch for d1. Possible values: open (0), close (1)
  - d2: consumed, enum, open, Switch for d2. Possible values: open (0), close (1)
  - TargetOutputVoltage: consumed, double, —, Voltage to be output.
  - TargetOutputCurrent: consumed, double, —, Current to be output.
  - Vdc: consumed, double, —, Measured voltage in the output circuit.
  - Idc: consumed, double, —, Measured current in the output circuit.
  - ExpectedWeldingDetectionState: consumed, enum, notExpected, Defines whether the WeldingDetection can be started. 'Welding check status' H'109.5.7 should be used to signal end of welding detection. Possible values: notExpected (0), expected (1)

[SmartCharging](../../CANoeCANalyzer/SmartCharging/SmartCharging.md) • [Message IDs](Callbacks/SCC_MessageID.md)
