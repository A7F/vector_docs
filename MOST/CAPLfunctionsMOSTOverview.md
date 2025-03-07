# MOST CAPL Functions

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/CAPLfunctionsMOSTOverview.md)

[CAPL Functions](../CAPLfunctions.md) » MOST CAPL Functions

**Valid for:** CANoe DE

## ON THIS PAGE:

- [Further Topics](#BMFurtherTopics)
- [Application Socket API](#ApplicationSocketAPI)
- [Evaluation of Event Procedures](#EvaluationEventProcedures)
- [Event Procedures](#EventProcedures)
- [Fault Injection](#FaultInjection)
- [Function Catalogue](#FunctionCatalogue)
- [Hardware API](#HardwareAPI)
- [Message Access](#MessageAccess)
- [Message Transmission](#MessageTransmission)
- [Selectors](#Selectors)
- [Test Functions](#TestFunctions)
- [Trace Highlighting](#TraceHighlighting)
- [Transmission and Receipt Settings of Nodes](#TransmissionReceiptSettingsNodes)

---

## Application Socket API

### Function Blocks

- **mostApRegister**: Registers a CAPL node at the Application Socket as function block.
- **mostApRegisterEx**: Registers a function block at the local function block list.
- **mostApUnregister**: Removes the function block assigned to a CAPL node from the Application Socket.
- **mostApUnregisterEx**: Removes a function block from the local function block list.

### Status

- **mostApGetFBlockID**: Returns the function block identifier (FBlockID) of the CAPL node.
- **mostApGetInstID**: Returns the instance identifier (InstID) of the CAPL node.
- **mostApIsAddressed**: Checks whether the functional MOST address {fblockID, instID} matches the CAPL node function blocks.
- **mostApIsRegistered**: Checks whether a function block assigned to the CAPL node is registered at the Application Socket.
- **mostApIsRegisteredEx**: Checks whether a function block is registered at the Application Socket.

### Read-Out of the Registries

The registries of the Application Socket may be read-out during the entire measurement cycle. For this purpose CAPL provides the following functions:

- **mostAsRgGetSize**: Returns the number of entries in the desired registry.
- **mostAsRgGetRxTxLog**: Returns the logical node address of a specific entry in the desired registry.
- **mostAsRgGetFBlockID**: Returns the FBlockID of a specific entry in the desired registry.
- **mostAsRgGetInstID**: Returns the InstID of a specific entry in the desired registry.

The 'regsel' parameter is used to select the desired registry:

- regsel = 1: [Local FBlockList](../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketLocalFBlockList.md)
- regsel = 2: [Bus Registry](../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketBusRegistry.md)

**Please note:** The Bus Registry is created in each device during MOST system configuration. It is only valid during network status 'ConfigOk'. Generally the NetworkMaster administers the Central Bus Registry. The Network Slaves mirror it in their De-Central Bus Registry.

Changes to registries are signaled in CAPL by the [OnMostAsRegistry()](EventProcedures/CAPLfunctionOnMOSTAsRegistry.md) event procedure.

[Example](Functions/CAPLfunctionMOSTExampleReadOutRegistries.md)

### Network State

- **mostGetNetState**: Returns the current network state of the MOST interface.

### MOST PowerMaster

- **mostPMResetOverTemperature**: Signalizes the PowerMaster that the device has reached operating temperature again.
- **mostPMSetOverTemperature**: Signalizes the PowerMaster that an over-temperature in its own device will be simulated.
- **mostPMShutDownStart**: Initiates a system shutdown by the PowerMaster.
- **mostPMShutDownCancel**: Aborts system shutdown of the PowerMaster.
- **mostPMTempShutdownWakeupTimeout**: Sets the timeout duration, after which the PowerMaster tries to wake-up the ring after an over-temperature shutdown.

### Gateway Node

If more than one MOST channel is allocated to a CAPL node (MOST-MOST gateway) the bus context must be defined before Application Socket functions are used. See [SetBusContext()](../Other/Functions/CAPLfunctionSetBusContext.md) regarding this.

### Notification Service

- **mostAsNtfDeviceIDListGetSize**: Returns the list size of all notification clients registered to a specific the function.
- **mostAsNtfDeviceIDListGetDeviceID**: Returns the deviceID of a specific entry in the notification list.
- **mostAsNtfEnable, mostAsNtfDisable**: Enables or disables the notification service for the function block assigned to the CAPL node.
- **mostAsNtfEnableEx**: Enables the notification service for a function block.
- **mostAsNtfDisableEx**: Disables the notification service for a function block.
- **mostAsNtfFunctionCheck**: Checks whether a notification client (deviceID) is registered in the notification matrix for a function.
- **mostAsNtfFunctionClear**: Clears a notification client entry from the notification matrix of a specific function.
- **mostAsNtfFunctionClearAll**: Clears all notification clients from the notification matrix of a specific function.
- **mostAsNtfFunctionEnable**: Enables the notification service for a specific function.
- **mostAsNtfFunctionDisable**: Disables the notification service for a specific function.
- **mostAsNtfFunctionIsEnabled**: Checks whether the notification service is enabled for a specific function.
- **mostAsNtfFunctionEnableEx**: Enables the notification service for a specific function of a function block not exclusively assigned to the CAPL node.
- **mostAsNtfFunctionDisableEx**: Disables the notification service for a specific function of a function block not exclusively assigned to the CAPL node.
- **mostAsNtfFunctionIsEnabledEx**: Checks whether the notification service is enabled for a specific function of a function block not exclusively assigned to the CAPL node.
- **mostAsNtfFunctionListGetSize**: Returns the list size of the functions for which a specific notification client is registered.
- **mostAsNtfFunctionListGetFunction**: Returns the function at a given index in the function list for which a specific notification client is registered.
- **mostAsNtfFunctionSet**: Registers a notification client in the notification matrix.
- **mostAsNtfOutput**: Sends a message via the notification service to a stated address.

### Shadow Service

- **mostAsShdDisable**: Removes an entry from the list of shadowed function blocks.
- **mostAsShdEnable**: Adds an entry to the list of shadowed function blocks.

### Notification Shadow Service

- **mostAsNtfShdFunctionEnable**: Registers a function to the notification shadow service.
- **mostAsNtfShdFunctionDisable**: Removes a function from the notification shadow service.

### Function Service

- **mostAsFsDisable**: Disables the function service for a function block assigned to the CAPL node.
- **mostAsFsDisableEx**: Disables the function service for a function block.
- **mostAsFsEnable**: Enables the function service for a function block assigned to the CAPL node.
- **mostAsFsEnableEx**: Enables the function service for a function block.
- **mostAsFsFunctionEnable**: Registers a function of the function block assigned to the CAPL node to the function service.
- **mostAsFsFunctionEnableEx**: Registers a function of a given function block to the function service.

### NetBlock

- **mostNBSetAbilityToWake**: Sets the AbilityToWake flag in the NetBlock.

### NetworkMaster

- **mostNwmFunctionEnable**: Registers and unregisters a function and its operations with the NetworkMaster.

## Evaluation of Event Procedures

### Functions for MOST Controller Events

- **mostEventChannel**: Returns the channel of a MOST controller event.
- **mostEventTime**: Returns the time stamp of a MOST controller event.
- **mostEventOrigTime**: Returns the hardware-generated time stamp of a MOST controller event.

### Functions for OnMostPkt()

- **mostPktArbitration**: Returns the packet arbitration value.
- **mostPktDestAdr**: Returns the destination address of the packet event.
- **mostPktDir**: Returns the direction of transmission.
- **mostPktDlc**: Number of transported data bytes of the packet.
- **mostPktGetData**: Copies the data bytes to a provided buffer.
- **mostPktGetSelData**: Copies the data bytes starting at a given position to a provided buffer.
- **mostPktIsSpy**: Returns whether the packet was received over the Spy of the asynchronous channel.
- **mostPktMsgChannel**: Returns the channel of the packet event.
- **mostPktMsgTime**: Returns the time stamp of the packet event.
- **mostPktOrigTime**: Returns the hardware generated time stamp of the packet event.
- **mostPktSrcAdr**: Returns the source address of the packet event.
- **mostPktTelID**: Returns the TelID of the packet.
- **mostPktTelLen**: Returns the TelLen of the packet.

### Functions for OnMostReg()

- **mostRegChip**: Returns the chip identifier.
- **mostRegDataLen**: Returns the number of bytes.
- **mostRegGetByteAbs**: Returns the byte value at a given position.
- **mostRegGetData**: Copies the data bytes to a provided buffer.
- **mostRegGetWordAbs**: Returns the word value at a given position.
- **mostRegOffset**: Returns the start address of the register.

## Event Procedures

### General Message / Packet Event Procedures

- **on mostAMSMessage**: Is called when a message is received from the Application Message Service (AMS).
- **OnMostEthPkt**: Is called when an Ethernet packet is received over the Packet Data channel.
- **OnMostEthPktFragment**: Is called when the spy detects an incomplete Ethernet packet transmission.
- **on mostMessage**: Is called on the receipt of a function catalog conform MOST frame.
- **OnMostMsgFragment**: Is called when the spy detects an incomplete transmission on the Control channel.
- **OnMostPkt**: Is called when a packet is received over the Asynchronous Channel.
- **OnMostPktFragment**: Is called when the spy detects an incomplete transmission on the Packet Data channel.
- **on mostRawMessage**: Is called on the receipt of MOST frames whose type isn't **Normal**.

### MOST High Protocol Observer and Combiner Event Procedures

- **OnMostMHPBlock**: Is called up as soon as a block from a MOST High connection has been fully transmitted.
- **OnMostMHPPacket**: Is called up as soon as a MOST High packet is finished.
- **OnMostMHPConnection**: Is called as soon as a MOST High connection version 2.2 or higher is terminated.
- **OnMostMHPError**: Is called up as soon as a MOST High protocol violation is observed.

### MOST Controller Event

- **OnMostAllBypass**: Is called if the bypass of the MOST chip was opened or closed.
- **OnMostAllocTable**: Is called as soon as the network interface detects a change in the MOST Allocation Table.
- **OnMostCriticalUnlock**: Is called when a critical unlock is detected.
- **OnMostEcl**: Is called when the state of the Electrical Control Line changed.
- **OnMostEclSequence**: Is called before the beginning and after the end of a sequence on the Electrical Control Line.
- **OnMostGroupAdr**: Is called when the group address changed.
- **on mostLightLockError**: Is called on controller events.
- **OnMostMacAdr**: Is called when the MAC address changed.
- **OnMostMPR**: Is called when the value of the MPR register changed (network change event (NCE)).
- **OnMostMPRDelayed**: Is called if the value of the MPR register has not changed since the last network change event (NCE) for t_MPRDelayed.
- **OnMostNodeAdr**: Is called when the node address changed.
- **OnMostNPR**: Is called when the value of node position register changed.
- **OnMostReg**: Is called in response to read or write requests to registers of a MOST network interface chip.
- **OnMostSBC**: Is called when the value of the synchronous bandwidth control register changed.
- **OnMostShutdownFlag**: Is called each time the state of the Shutdown flag changes.
- **OnMostShutdownReason**: Is called each time when the shutdown reason changes.
- **OnMostStableLock**: Is called when stable lock is detected.
- **OnMostStress**: Is called before the beginning and after the end of the stress generation.
- **OnMostSyncAudio**: Is called after routing of audio input or output of the network interface.
- **OnMostSyncSpdif**: Is called after routing of S/PDIF input or output of the network interface.
- **OnMostSystemLock**: Is called each time the state of the System-Lock flag changes.
- **OnMostTimingMode**: Is called if the timing mode of the MOST hardware has been changed.
- **OnMostTxLight**: Is called as soon as the light at the output goes on/off.

### MOST Application Events

- **OnMostNetOn, OnMostInitReady**: Is called when the NetOn / InitReady event (first "Stable Lock" after he loop has been woken up) has occurred.
- **OnMostNetState**: Is called when the network status is changed.
- **OnMostApInstID**: Is called when the InstID of the associated function block changes.
- **OnMostAsRegistry**: Is called when the Local FBlockList or Bus Registry is changed.

### Fault Injection

- **OnMostFiAmsPreReceive**: Is called before an AMS message is received.
- **OnMostFiAmsPreSend**: Is called before an AMS message is sent.

## Fault Injection

- **mostAsFiEnable**: Enables/disables fault injection for CANoe’s Application Socket services.
- **mostFiAmsReceive**: Pretends an AMS message reception to the Application Socket or CAPL node.
- **mostNwmFiEnableRingScan**: Changes the ring scan behavior of CANoe’s NetworkMaster.
- **mostNwmFiSetConfigState**: Forces the network configuration status to be set in CANoe’s NetworkMaster.
- **mostNwmFiSetParameter, mostNwmFiGetParameter**: Provide access to the timing parameters of CANoe’s NetworkMaster implementation.

## Function Catalogue

- **mostAmsOutput**: Definition and direct dispatch of an AMS message using the syntax from the MOST specification and the description in the XML function catalog.
- **mostMsgDecodeRLE**: Decodes the data area of a message and saves the function IDs in a list.
- **mostMsgEncodeRLE**: Encodes a list of function IDs and saves it in the data area of a message.
- **mostMsgGetSymbols**: Determining the symbolic Names of the function block, the function and the Optype from an AMS or control message using the XML function catalog.
- **mostMsgSet**: Populating an AMS message using the syntax from the MOST specification and the description in the XML function catalog.
- **mostParamGet**: Query of a parameter value from an AMS message using the parameter name from the XML function catalog.
- **mostParamGetData**: Query of parameters of the String type or RawStream from an AMS message using the parameter name from the XML function catalog.
- **mostParamGetString**: Query of parameters of the String type from an AMS message using the parameter name from the XML function catalog.
- **mostParamGetStringAscii**: Query of parameters of the String type from an AMS message and decode to ASCII format.
- **mostParamIsAvailable**: Check whether a described parameter with the parameter name from the XML function catalog is in an AMS message.
- **mostParamSet**: Setting of a parameter value in an AMS message using the parameter name from the XML function catalog.
- **mostParamSetData**: Setting of parameters of the String type or RawStream in an AMS message using the parameter name from the XML function catalog.
- **mostParamSetString**: Setting of parameters of the String type (for ASCII-coded strings only) or of the 'Enum' type in an AMS message using the parameter name from the XML function catalog.
- **mostParamSetStringEnc**: Encoding and setting of parameters of the String type (for ASCII-coded strings only).
- **mostStringToAscii**: Convert MOST string to ASCII string.

## Hardware API

### Electrical Control Line

- **mostConfigureEclSequence**: Defines a signal sequence for the Electrical Control Line and prepares the hardware to start the generation.
- **mostGenerateEclSequence**: Starts the generation of a signal sequence on the Electrical Control Line.
- **mostGetEcl**: Returns the current state of the Electrical Control Line.
- **mostSetEcl**: Switches the Electrical Control Line.
- **mostGetEclTermination**: Returns the current setting of the Electrical Control Line resistor.
- **mostSetEclGlitchFilter**: Configures the timing of the glitch filter for the ECL line.
- **mostSetEclTermination**: Switches the Electrical Control Line resistor.

### Node Addresses - Node Mode

- **mostGetAltPktAdr**: Returns the current alternative packet address of the MOST interface.
- **mostGetGroupAdr**: Returns the current group address of the MOST interface.
- **mostGetNodeAdr**: Returns the current node address of the MOST interface.
- **mostGetNodePosAdr**: Returns the current node position address of the MOST interface.
- **mostSetAltPktAdr**: Sets the alternative packet address of the MOST interface.
- **mostSetGroupAdr**: Sets the group address of the MOST interface.
- **mostSetNodeAdr**: Sets the node address of the MOST interface.
- **mostSetOwnAdr**: Sets the node and group address of the MOST interface.
- **mostSetMacAdr, mostGetMacAdr**: Sets/gets the MAC address of the MOST interface.

### Ring State

- **mostAllocTableGetCL**: Returns the connection label of the respective entry in the allocation table.
- **mostAllocTableGetSize**: Returns the number of entries (connection labels) in the allocation table.
- **mostAllocTableGetWidth**: Returns the number of channels of the respective entry (connection label) in the allocation table.
- **mostGetAllocTable**: Copies the MOST Allocation Table to a local buffer.
- **mostGetCodingErrors**: Returns the number of coding errors.
- **mostGetLock**: Returns the current lock status (unlock, lock).
- **mostGetLockEx**: Returns the current lock status (unlock, lock, stable lock, critical unlock).
- **mostGetMPR**: Returns the current value of the MPR register (number of nodes in the ring).
- **mostGetNPR**: Returns the current value of the NPR register (current node position in the ring).
- **mostGetNceType**: Returns the type of NCE (can only be called within [OnMostMPR](EventProcedures/CAPLfunctionOnMOSTMPR.md)).
- **mostGetRxLight**: Returns the current light status at the FOT input.
- **mostGetSBC**: Returns the current value of the SBC register.
- **mostGetShutdownReason**: Retrieves the last shutdown reason value.
- **mostGetShutdownFlag**: Returns the current state of the Shutdown flag.
- **mostGetSystemLock**: Returns the current state of the System Lock Flag.
- **mostGetTxLight**: Returns the current light status at the FOT output.
- **mostSetCorrectStartupSBC**: Activates or deactivates the correct setting of the 'Synchronous Bandwidth Control' register (SBC) in the MOST chip.
- **mostSetShutdownReason**: Sets the shutdown reason value.
- **mostSetSBC**: Sets the value of the SBC register.
- **mostSetTxLight**: Sets the light status at the FOT output.
- **mostShutDown**: Performs a network shutdown.
- **mostWakeup**: Generates an optical wake-up signal.

### Register Access

- **mostReadReg**: Initiates read-out of the registers of a MOST hardware chip.
- **mostWriteReg**: Writes to one or more registers of a MOST hardware chip.

### Synchronous Channel Allocation Service

- **mostSyncAlloc**: Reserves bandwidth for sending data on the synchronous channel.
- **mostSyncDealloc**: Releases reserved bandwidth on the synchronous channel.

### Operating Modes

#### Bypass Mode

- **mostGetAllBypass**: Returns the current bypass status of the MOST interface.
- **mostSetAllBypass**: Disables or enables the bypass of the MOST interface.

#### Timing Mode

- **mostSetMasterMode, mostGetMasterMode**: Configures the timing master as static or non-static master.
- **mostGetTimingMode**: Returns the current timing mode of the MOST interface.
- **mostSetTimingMode**: Sets the timing mode of the MOST interface.

#### Spy Mode

- **mostGetSpyAsync**: Returns the current asynchronous spy status of the MOST interface.
- **mostGetSpyCtrl**: Returns the current control spy status of the MOST interface.
- **mostGetSpyEthPkt**: Returns the current Ethernet packet spy status of the MOST interface.
- **mostSetSpyAsync**: Disables or enables the asynchronous spy of the MOST interface.
- **mostSetSpyCtrl**: Disables or enables the control spy of the MOST interface.
- **mostSetSpyEthPkt**: Disables or enables the Ethernet packet spy of the MOST interface.

#### Stress Mode

- **mostConfigureBusloadAsync**: Configures the busload generator for the asynchronous channel.
- **mostConfigureBusloadCtrl**: Configures the busload generator for the control channel.
- **mostConfigureBusloadEthPkt**: Configures the busload generator for the Ethernet channel.
- **mostGenerateBusloadAsync**: Sends cyclical packets to the asynchronous channel.
- **mostGenerateBusloadCtrl**: Sends cyclical messages to the control channel.
- **mostGenerateBusloadEthPkt**: Configures the busload generator for the Ethernet channel.
- **mostGenerateBypassToggle**: Starts or stops generation of Bypass-open-close transitions.
- **mostSetRxBufferAsync**: Starts or stops draining of the asynchronous receive buffer and allows to provoke low level retries.
- **mostSetShutDownFlagUsage, mostGetShutDownFlagUsage**: Switches usage of shutdown flag.
- **mostSetStressNodeParameter, mostGetStressNodeParameter**: Configures the stress network interface controller.
- **mostSetStressNodeParameterData**: Configures the stress network interface controller with a byte sequence.
- **mostSetSystemLockFlagUsage, mostGetSystemLockFlagUsage**: Switches usage of system lock flag.
- **mostSetTxLightPower**: Sets the intensity of the light at the Fiber Optical Transmitter (FOT).
- **mostSetRxBufferCtrl**: Disables or enables the Rx buffer for messages of the control channel.
- **mostGenerateLightError**: Starts or stops generation of Light-ON-OFF transitions.
- **mostGenerateLockError**: Starts or stops generation of Light Unmodulated-Modulated transitions.
- **mostSetRetryParameter, mostGetRetryParameter**: Provides access to the transceiver chip parameters for message transmission.

### Audio

- **mostGetSyncMute**: Returns the current mute status of the audio input or output of the MOST interface.
- **mostGetSyncVolume**: Returns the current volume of the audio input or output of the MOST interface.
- **mostSetSyncAudio**: Programs the routing engine for the audio input or output of the MOST interface.
- **mostSetSyncMute**: Activates or deactivates the audio input or output of the MOST interface.
- **mostSetSyncVolume**: Sets the volume of the audio input or output of the MOST interface.

### S/PDIF

- **mostGetSyncSpdifMode**: Returns the timing mode of the S/PDIF signal.
- **mostGetClockSource**: Returns the clock source of the timing master.
- **mostSetSyncSpdif**: Programs the routing engine for S/PDIF input or output of the MOST interface.
- **mostSetSyncSpdifLock**: Locks the internal S/PDIF timing generator on the S/PDIF input data stream.
- **mostSetSyncSpdifMode**: Sets the timing mode for the S/PDIF signal.
- **mostSetClockSource**: Sets the clock source for the timing master.

### Other

- **mostGetHWCapability**: Returns specific properties of the attached MOST interface.
- **mostGetHWInfo**: Returns specific information of the attached MOST interface (e.g. hardware type).
- **mostGetSpecVersion**: Returns the applied specification version of a MOST channel.
- **mostGetSpeedGrade**: Returns the configured speed grade of a MOST channel.
- **mostTwinklePowerLed**: Twinkles the power LED.

## Message Access

- **mostPrepareReport**: Preparation of an AMS message as response (OpType>=9) to a received command message (OpType<9).
- **getThisMessage**: Copies the data of an AMS message into a message variable - Deprecated - see [Initialization of Message Variables](CAPLfunctionsMOSTInitializationMessageVariables.md)!

## Message Transmission

- **output**: Sends a message on the MOST ring.
- **outputMostEthPkt**: Sends out an Ethernet packet over the asynchronous channel.
- **outputMostEthPktThis**: Passes the Ethernet packet on to the next node in the nodal sequence.
- **outputMostPkt**: Sends a packet on the MOST ring.
- **outputMostPktThis**: Passes the packet on to the next node in the nodal sequence.
- **mostAmsOutput**: Definition and direct dispatch of an AMS message using the syntax from the MOST specification and the description in the XML function catalog.
- **mostAmsClearTxQueue**: Clears all entries in the AMS send buffer.
- **mostAmsSetSizePrefixed**: Configures the minimum length of an AMS message above which the size prefixed mode is used.
- **mostSendError**: Generates and sends an error message directly based on a received command message.

## Selectors

- **mostMessage and mostAMSmessage**: Detailed description of the mostMessage and mostAMSmessage selectors
- **mostRawMessage**: Detailed description of the mostRawMessage selectors
- **mostLightLockError**: Detailed description of the mostLightLockError selectors

## Test Functions

### Message Events

- **TestGetWaitEventMostAMSMsgData**: Retrieves the AMS message data of a waiting condition.
- **TestGetWaitEventMostPkt**: Provides access to packet data of a waiting condition.
- **TestGetWaitEventMostRawMsgData**: Retrieves the CMS raw message data of a waiting condition.
- **TestGetWaitEventMostMsgData**: Retrieves the CMS message data of a waiting condition.
- **TestJoinMostAMSMessageEvent**: Adds an AMS message to the set of joined events.
- **TestJoinMostAMSReportEvent**: Adds an AMS report message (OpType > 8) to the set of joined events.
- **TestJoinMostAMSSpyMessageEvent**: Adds an AMS spy message to the set of joined events.
- **TestJoinMostAMSSpyReportEvent**: Adds an AMS spy report message (OpType > 8) to the set of joined events.
- **TestJoinMostMessageEvent**: Adds a CMS message to the set of joined events.
- **TestJoinMostPktEvent**: Adds a packet to the set of joined events.
- **TestJoinMostReportEvent**: Adds a CMS report message (OpType > 8) to the set of joined events.
- **TestJoinMostSpyMessageEvent**: Adds a CMS spy message to the set of joined events.
- **TestJoinMostSpyPktEvent**: Adds a spy packet to the set of joined events.
- **TestJoinMostSpyReportEvent**: Adds a CMS spy report message (OpType > 8) to the set of joined events.
- **TestSendMostAMSMessage**: Sends an AMS message an waits for Tx acknowledgment result.
- **TestSendMostRawMessage**: Send a CMS raw message and waits for Tx acknowledgment result.
- **TestWaitForMostAMSMessage**: Waits for specific AMS message.
- **TestWaitForMostAMSReport**: Waits for specific AMS report message (OpType > 8).
- **TestWaitForMostAMSRespons**: Sends a symbolically defined AMS message and waits for the appropriate response message.
- **TestWaitForMostAMSResult**: Sends a symbolically defined AMS message with OpType ‘StartResult’ or ‘StartResultAck’ and waits for the reception of the appropriate ‘Result’ or ‘ResultAck’ message.
- **TestWaitForMostAMSSpyMessage**: Waits for specific AMS spy message.
- **TestWaitForMostAMSSpyReport**: Waits for specific AMS spy report message (OpType > 8).
- **TestWaitForMostMessage**: Waits for specific CMS message.
- **TestWaitForMostPkt**: Waits for a specific packet.
- **TestWaitForMostRawSpyMessage**: Waits for specific CMS raw spy message.
- **TestWaitForMostReport**: Waits for specific CMS report message (OpType > 8).
- **TestWaitForMostSpyMessage**: Waits for specific CMS spy message.
- **TestWaitForMostSpyPkt**: Waits for a specific spy or node packet.
- **TestWaitForMostSpyReport**: Waits for specific CMS spy report message (OpType > 8).

### Controller Events

- **TestWaitForMostAllBypass**: Wait for a bypass change event.
- **TestWaitForMostCriticalUnlock**: Wait for the occurrence of a LightLock event indicating a **critical unlock** state.
- **TestWaitForMostGroupAdr**: Waits for group address change event.
- **TestWaitForMostLightOff**: Wait for the occurrence of a LightLock event indicating a **no Light & no Lock** state.
- **TestWaitForMostMPR**: Waits for a MPR event (NCE).
- **TestWaitForMostNetState**: Waits for NetState change event.
- **TestWaitForMostNodeAdr**: Waits for a node address change event.
- **TestWaitForMostNPR**: Waits for a NPR change event.
- **TestWaitForMostSBC**: Wait for SBC change event.
- **TestWaitForMostShortUnlock**: Wait for the occurrence of a LightLock event indicating a **Light & no Lock** state.
- **TestWaitForMostStableLock**: Wait for the occurrence of a LightLock event indicating a **stable unlock** state.
- **TestMostReadReg**: Reads one or several MOST chip registers and waits for the result.
- **TestMostRegGetData**: Retrieve the register values after a [TestMostReadReg](../Test/Functions/CAPLfunctionTestMostReadReg.md) or [TestMostWriteReg](../Test/Functions/CAPLfunctionTestMostWriteReg.md) function was called.
- **TestMostWriteReg**: Writes one or several MOST chip registers and waits for the result.

Further links: | [TestWaitForAllJoinedEvents](../Test/Functions/CAPLfunctionTestWaitForAllJoinedEvents.md) | [TestWaitForAnyJoinedEvent](../Test/Functions/CAPLfunctionTestWaitForAnyJoinedEvent.md) |

## Trace Highlighting

- **mostEthPktSetTraceColors**: Sets the text and background color for displaying the MOST event in the Trace Window.
- **mostMHPBlockSetTraceColors**: Sets the text and background color for displaying the MOST event in the Trace Window.
- **mostMHPConnectionSetTraceColors**: Sets the text and background color for displaying the MOST event in the Trace Window.
- **mostMHPErrorSetTraceColors**: Sets the text and background color for displaying the MOST event in the Trace Window.
- **mostMHPPacketSetTraceColors**: Sets the text and background color for displaying the MOST event in the Trace Window.
- **mostPktSetTraceColors**: Sets the text and background color for displaying the MOST event in the Trace Window.
- **traceSetEventColors**: Sets the text and background color for displaying the MOST event in the Trace Window.

## Transmission and Receipt Settings of Nodes

- **mostApplicationNode**: Switches the CAPL node into application mode - only messages (no spy!) are received/sent from/on channels to which the CAPL node is connected to.
- **mostGetChannel**: Returns the channel number to which the CAPL node is connected to.
- **mostRcvSpyMessagesOnly**: The MOST message handling routines of this node are only called if the message was received by the Spy of the network interfaces.
- **mostStrictChannelMapping**: The MOST sending and receiving behavior of the node is strictly based on the configuration in the Simulation Setup.

## Further Topics

- [Option .MOST](../../CANoeCANalyzer/MOST/MOST.md)
- [MOST Simulation Concept](../../CANoeCANalyzer/MOST/MOSTSimulation.md)
- [PowerMaster](../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketPowerMaster.md)
- [Error Codes of CAPL functions](CAPLfunctionsMOSTErrorCodes.md)
- [Initialization of message variables](CAPLfunctionsMOSTInitializationMessageVariables.md)
- [Symbolic identification of parameters](CAPLfunctionsMOSTSymIDParam.md)
- [Symbolic identification of messages](CAPLfunctionsMOSTSymIDMMessage.md)
- [General tips on XML function catalog support in CAPL](CAPLfunctionsMOSTXMLSupport.md)
- [MOST high observer and combiner](CAPLfunctionsMOSTHighObserverCombiner.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)