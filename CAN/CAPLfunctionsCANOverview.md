# CAN CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## ON THIS PAGE:

- [Bus Statistics](#BMBusStatistics)
- [CANdb API](#CANdbAPI)
- [Event Procedures](#EventProcedures)
- [General Functions](#GeneralFunctions)
- [Hardware API](#HardwareAPI)
- [Selectors](#Selectors)
- [Statistics API](#StatisticsAPI)

## Bus Statistics 

- **[canEnableStatistics](Functions/CAPLfunctionCanEnableStatistics.md):** Enables or disables CAN statistics on a specific (Form 1) or all (Form 2) CAN channels.
- **[canGetBurstsCount](Functions/CAPLfunctionCanGetBurstsCount.md):** Gets the total count of bursts of a CAN channel.
- **[canGetBurstTime](Functions/CAPLfunctionCanGetBurstTime.md):** Gets the burst time of a CAN channel in microseconds.
- **[canGetBusLoad](Functions/CAPLfunctionCanGetBusLoad.md):** Gets the busload of a CAN channel in percent.
- **[canGetChipState](Functions/CAPLfunctionCanGetChipState.md):** Gets the current chip state of a CAN channel.
- **[canGetErrorFrameCount](Functions/CAPLfunctionCanGetErrorFrameCount.md):** Gets the total count of error frames of a CAN channel.
- **[canGetErrorFrameRate](Functions/CAPLfunctionCanGetErrorFrameRate.md):** Gets the error frame rate of a CAN channel in frames per second [fr/s].
- **[canGetExtDataCount](Functions/CAPLfunctionCanGetExtDataCount.md):** Gets the total count of extended data frames of a CAN channel.
- **[canGetExtDataRate](Functions/CAPLfunctionCanGetExtDataRate.md):** Gets the rate of extended data frames of a CAN channel in frames per second [fr/s].
- **[canGetExtRemoteCount](Functions/CAPLfunctionCanGetExtRemoteCount.md):** Gets the total count of extended remote frames of a CAN channel.
- **[canGetExtRemoteRate](Functions/CAPLfunctionCanGetExtRemoteRate.md):** Gets the rate of extended remote frames of a CAN channel in frames per second [fr/s].
- **[canGetFramesPerBurstCount](Functions/CAPLfunctionCanGetFramesPerBurstCount.md):** Gets the count of frames per burst of a CAN channel.
- **[canGetMinSendDistance](Functions/CAPLfunctionCanGetMinSendDistance.md):** Gets the minimum distance between two consecutive frames of a CAN channel in milliseconds.
- **[canGetOverloadFrameCount](Functions/CAPLfunctionCanGetOverloadFrameCount.md):** Gets the total count of overload frames of a CAN channel.
- **[canGetOverloadFrameRate](Functions/CAPLfunctionCanGetOverloadFrameRate.md):** Gets the rate of overload frames of a CAN channel in frames per second [fr/s].
- **[canGetRxErrorCount](Functions/CAPLfunctionCanGetRxErrorCount.md):** Gets the total count of receive errors of a CAN channel.
- **[canGetStdDataCount](Functions/CAPLfunctionCanGetStdDataCount.md):** Gets the total count of standard data frames of a CAN channel.
- **[canGetStdDataRate](Functions/CAPLfunctionCanGetStdDataRate.md):** Gets the rate of standard data frames of a CAN channel in frames per second [fr/s].
- **[canGetStdRemoteCount](Functions/CAPLfunctionCanGetStdRemoteCount.md):** Gets the total count of standard remote frames of a CAN channel.
- **[canGetStdRemoteRate](Functions/CAPLfunctionCanGetStdRemoteRate.md):** Gets the rate of standard remote frames of a CAN channel in frames per second [fr/s].
- **[canGetTransceiverErrorCount](Functions/CAPLfunctionCanGetTransceiverErrorCount.md):** Gets the total count of transceiver errors of a CAN channel.
- **[canGetTxErrorCount](Functions/CAPLfunctionCanGetTxErrorCount.md):** Gets the total count of transmit errors of a CAN channel.

## CANdb API 

- **[getFirstCANdbFilename](Functions/CAPLfunctionGetFirstCANdbFileName.md):** Finds out the filename of the first assigned database.
- **[getFirstCANdbName](Functions/CAPLfunctionGetFirstCANdbName.md):** Finds out the name of the first assigned database.
- **[getSignalName](Functions/CAPLfunctionGetSignalName.md):** Returns the signal name at indexed positions (start bit) in the payload of a CAN message for CAN networks. (Form 1) Returns the signal name at indexed positions (start bit) of a PDU for CAN networks. (Form 2)
- **[getMessageAttrInt](Functions/CAPLfunctionGetMessageAttrInt.md):** Gets the value of a message attribute from the database.
- **[GetMessageID](Functions/CAPLfunctionGetMessageID.md):** Finds out the message ID.
- **[GetMessageName](Functions/CAPLfunctionGetMessageName.md):** Finds out the message name.
- **[getNextCANdbFilename](Functions/CAPLfunctionGetNextCANdbFileName.md):** Finds out the filenames of the other assigned databases.
- **[getNextCANdbName](Functions/CAPLfunctionGetNextCANdbName.md):** Finds out the names of the other assigned databases.
- **[setSignalStartValues](Functions/CAPLfunctionSetSignalStartValues.md):** Sets the values of the signals in the parameter to the start values defined in the database.

## Event Procedures 

- **[on busIntegration](EventProcedures/CAPLfunctionOnBusIntegration.md):** Is called when a CAN channel is Bus Integrated (e.g. after the start of measurement, rest or bit timing changed).
- **[on errorFrame](EventProcedures/CAPLfunctionOnErrorFrame.md):** Occurrence of an Error Frame.
- **[on message](EventProcedures/CAPLfunctionOnMessage.md):** Receipt of a CAN message.
- **[on signal](../../Shared/CAPL/SignalOrientedProgramming/SOPSignalChange.md):** Is called with every signal change.
- **[on signal_change](../../Shared/CAPL/SignalOrientedProgramming/SOPSignalChange.md):** Is called with every signal change.
- **[on signal_update](../../Shared/CAPL/SignalOrientedProgramming/SOPSignalChange.md):** Is called with every signal reception.

### Events of CAN controller

- **on busOff:** CAN controller goes to Bus Off.
- **on errorActive:** CAN controller goes to ErrorActive.
- **on errorPassive:** CAN controller goes to ErrorPassive.
- **on warningLimit:** CAN controller reaches the Warning Limit.

## General Functions 

- **[canConfigureBusOff](Functions/CAPLfunctionCanConfigureBusOff.md):** Sets the bus state to **BussOff**.
- **[canGetDataLength](Functions/CAPLfunctionCanGetDataLength.md):** Returns the valid payload length of the can message.
- **[canOutputErrorFrame](Functions/CAPLfunctioncanOutputErrorFrame.md):** Outputs an Error Frame to the CAN bus.
- **[getPayloadData](Functions/CAPLfunctionGetPayloadData.md):** Returns the valid payload of a frame that was interrupted during transmission.
- **[isStdId](Functions/CAPLfunctionIsStdLd.md):** Checks parameter for standard identifier.
- **[isExtId](Functions/CAPLfunctionIsStdLd.md):** Checks parameter for [extended identifier](../../CANoeCANalyzer/General/CANExtendedIdentifier.md).
- **[mkExtId](Functions/CAPLfunctionMkExtID.md):** Returns an extended ID.
- **[output](Functions/CAPLfunctionOutput.md):** Outputs a message or an Error Frame from the program block.
- **[valOfId](Functions/CAPLfunctionValOfId.md):** Returns the value of a message identifier independent of its type.

## Hardware API 

- **[canActivateTxSelfAck](Functions/CAPLfunctionCanActivateTxSelfAck.md):** Activates/deactivates the transmit [self ack feature](../../CANoeCANalyzer/Ribbon/Hardware/NetworkHardware/NetworkHardwareCANControllerConfiguration.md) for the defined channel.
- **[canFdGetConfiguration](Functions/CAPLfunctionCanFdSetConfiguration.md):** Gets the CAN controller parameters for arbitration and data phase.
- **[canFdSetConfiguration](Functions/CAPLfunctionCanFdSetConfiguration.md):** Sets the CAN controller parameters for arbitration and data phase.
- **[canFlushTxQueue](Functions/CAPLfunctionCanFlushTxQueue.md):** Flushes the Tx queue for the defined channel.
- **[canGetConfiguration](Functions/CAPLfunctionCanGetSetConfiguration.md):** Reads the CAN controller parameters.
- **[canSetChannelAcc](Functions/CAPLfunctionCanSetChannelAcc.md):** Sends received messages through to your CANoe DE product via an acceptance filter.
- **[canSetChannelMode](Functions/CAPLfunctionCanSetChannelMode.md):** Activates/deactivates the TXRQ of the CAN controller.
- **[canSetChannelOutput](Functions/CAPLfunctionCanSetChannelOutput.md):** Defines the response of the CAN controller to the bus traffic and sets the ACK bit.
- **[canSetConfiguration](Functions/CAPLfunctionCanGetSetConfiguration.md):** Sets the CAN controller parameters.
- **[GetCanBittimingConfiguration](Functions/CAPLfunctionGetSetCanBittimingConfiguration.md):** Returns the configured bit timings.
- **[getCardTypeEx](Functions/CAPLfunctionGetCardTypeEx.md):** Determines the card type of CAN channel.
- **[getChipType](Functions/CAPLfunctionGetChipType.md):** Determines the type of CAN controller used.
- **[resetCan](Functions/CAPLfunctionResetCan.md):** Resets the CAN controller.
- **[ResetCanEx](Functions/CAPLfunctionResetCanEx.md):** Resets the CAN controller for one specific CAN channel.
- **[ScanBaudrateActive](Functions/CAPLfunctionScanBaudrateActive.md):** Determines the baudrate for the given channel.
- **[ScanBaudratePassive](Functions/CAPLfunctionScanBaudratePassive.md):** Starts the scan and detects the baudrate on the given channel.
- **[setBtr](Functions/CAPLfunctionSetBtr.md):** Sets another baudrate.
- **[SetCanBittimingConfiguration](Functions/CAPLfunctionGetSetCanBittimingConfiguration.md):** Configures the bit timings.
- **[setOcr](Functions/CAPLfunctionSetOcr.md):** Sets the Output Control Register.

## Selectors 

- **[Message](CAPLfunctionMessageSelectors.md):** Detailed description of the CAN [message](../../Shared/CAPL/General/DeclarationOfMessages.md) selectors.
- **[ErrorFrame](CAPLfunctionErrorFrameSelectors.md):** Detailed description of the CAN Error Frame selectors.

## Statistics API 

- **[canResetStatistics](Functions/CAPLfunctionCanResetStatistics.md):** Resets CAN statistics.
- **[BusLoad](Functions/CAPLfunctionBusLoad.md):** Returns the current busload of a channel.
- **[ChipState](Functions/CAPLfunctionChipState.md):** Returns the current chip state of the CAN controller.
- **[ExtendedFrameRate](Functions/CAPLfunctionExtendedFrameRate.md):** Returns the current rate of extended CAN messages on a channel.
- **[ExtendedRemoteFrameRate](Functions/CAPLfunctionExtendedRemoteFrameRate.md):** Returns the number of extended remote CAN messages on a channel since start of measurement.
- **[RxChipErrorCount](Functions/CAPLfunctionRxChipErrorCount.md):** Returns the current Rx error count in the receiver of a channel.
- **[StandardFrameRate](Functions/CAPLfunctionStandardFrameRate.md):** Returns the current rate of standard CAN messages on a channel.
- **[StandardRemoteFrameRate](Functions/CAPLfunctionStandardRemoteFrameRate.md):** Returns the current rate of standard CAN messages on a channel.
- **[TxChipErrorCount](Functions/CAPLfunctionTxChipErrorCount.md):** Returns the current number of Tx errors in the CAN receiver of a channel.
