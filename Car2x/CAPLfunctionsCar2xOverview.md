# Car2x CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

## Car2x

- Only available with Option Car2x.
- The Car2x Interaction Layer (Car2x IL) simplifies the simulation of a Car2x node with CAPL and allows to send and receive individual WLAN packets.
- To use the CAPL functions the [C2X_IL.dll](../../CANoeCANalyzer/Car2x/procedures/c2xProceduresSimStim/c2xIncludeCar2xIL.md) must be included.

**ON THIS PAGE:**

- [Callback Functions](#Callback)
- [Car2x IL API](#Car2xILAPI)
- [Car2x Stack API](#StackAPI)
- [Car2x Test Service Library](#TestAPI)
- [General Functions](#GeneralFunctions)
- [Packet API](#PacketAPI)
- [Protocol Analyzer API](#ProtocolAnalyzerAPI)
- [Scenario API](#ScenarioAPI)
- [Security API](#SecurityAPI)
- [Station API](#StationAPI)
- [Time API](#TimeFunctions)

## Callback Functions

- **`<OnC2xPacket>`**: [CAPL handler to receive data of WLAN packets.](Callbacks/CAPLfunctionC2xOnC2xPacket.md)
- **`<OnC2xTransmitPacket>`**: [CAPL handler to modify database defined WLAN packets before transmission.](Callbacks/CAPLfunctionC2xOnC2xTransmitPacket.md)
- **OnProtocolViolation**: [A CAPL callback function informing you about a new Protocol Analyzer finding.](Callbacks/CAPLfunctionC2xOnProtocolViolation.md)
- **OnScenarioStateChanged**: [Is called when the state of the scenario was changed.](Callbacks/CAPLfunctionC2xOnScenarioStateChanged.md)
- **OnStartScenario**: [Is called at the time when the scenario start was triggered.](Callbacks/CAPLfunctionC2xOnStartScenario.md)
- **OnStationAttributeTrigger**: [Defines a reaction on triggerable attributes of a scenario station.](Callbacks/CAPLfunctionC2xOnStationAttributeTrigger.md)
- **OnStationAttributeTriggerAll**: [Defines a reaction on all triggerable attributes of all stations in the scenario.](Callbacks/CAPLfunctionC2xOnStationAttributeTriggerAll.md)

## Car2x IL API

- **C2xConfigureChannel**: [Redefines some or all channel parameters on the fly.](Functions/CAPLfunctionC2xConfigureChannel.md)
- **C2xDisableMsg**: [Disables a message that is enabled.](Functions/CAPLfunctionC2xDisableMsg.md)
- **C2xDispatchPacket**: [Dispatches a packet to CANoe DE product application.](Functions/CAPLfunctionC2xDispatchPacket.md)
- **C2xEnableCV2xMode**: [Enables the CV2x protocol for a channel.](Functions/CAPLfunctionC2xEnableCV2xMode.md)
- **C2xEnableMsg**: [Enables a message that is disabled.](Functions/CAPLfunctionC2xEnableMsg.md)
- **C2xGetChannelConfiguration**: [Retrieves the current configuration parameters of a specific hardware channel.](Functions/CAPLfunctionC2xGetChannelConfiguration.md)
- **C2xGetCycleTime**: [Gets the cycle time for a message.](Functions/CAPLfunctionC2xGetCycleTime.md)
- **C2xGetMessageName**: [Get application layer name of a message.](Functions/CAPLfunctionC2xGetMessageName.md)
- **C2xIsMsgEnabled**: [Check if a message is enabled.](Functions/CAPLfunctionC2xIsMsgEnabled.md)
- **C2xIsNodeStarted**: [Check if the node is started.](Functions/CAPLfunctionC2xIsNodeStarted.md)
- **C2xSendMsg**: [Send the message with the specified message name.](Functions/CAPLfunctionC2xSendMsg.md)
- **C2xSetCycleTime**: [Sets the cycle time for a message.](Functions/CAPLfunctionC2xSetCycleTime.md)
- **C2xSetSendParameters**: [Sets transmission relevant send parameters.](Functions/CAPLfunctionC2xSetSendParameters.md)
- **C2xSetSignal**: [Sets a signal in a packet.](Functions/CAPLfunctionC2xSetSignal.md)
- **C2xStartNode**: [Start transmission of messages for node.](Functions/CAPLfunctionC2xStartNode.md)
- **C2xStopNode**: [Stop transmission of messages for node.](Functions/CAPLfunctionC2xStopNode.md)

## Car2x Protocol Analyzer API

- **C2xReportProtocolViolation**: [Publish the Protocol Analyzer rule violation.](Functions/CAPLfunctionC2xReportProtocolViolation.md)
- **C2xProtocolAnalyzerGetRuleList**: [Copies the multiline text representation of the Car2x Protocol Analyzer rules to the variable specified by buffer function parameter.](Functions/CAPLfunctionC2xProtocolAnalyzerGetRuleList.md)

## Car2x Stack API

- **C2xAddGeoPos**: [Sets the current geographical position of the station.](Functions/CAPLfunctionC2xAddGeoPos.md)
- **C2xApplyPathHistory**: [Applies path history data to the packet.](Functions/CAPLfunctionC2xApplyPathHistory.md)
- **C2xResetPathHistory**: [Clears previously stored path history data.](Functions/CAPLfunctionC2xResetPathHistory.md)

## Car2x Test Service Library

- **C2xTestGetWaitForMessage**: [Retrieves the Car2x message that has led to the resume of the last wait statement.](Functions/CAPLfunctionC2xTestGetWaitForMessage.md)
- **C2xTestJoinMessage**: [Joins a Car2x message to the current set of waiting events.](Functions/CAPLfunctionC2xTestJoinMessage.md)
- **C2xTestJoinSignalInRange**: [Joins a Car2X message which has a signal that is inside or equals the given limits to the current set of waiting events](Functions/CAPLfunctionC2xTestJoinSignalInRange.md)
- **C2xTestJoinSignalMatch**: [Joins a Car2X message which has a signal that matches the given value to the current set of waiting events](Functions/CAPLfunctionC2xTestJoinSignalMatch.md)
- **C2xTestWaitForMessage**: [Waits for a Car2x message.](Functions/CAPLfunctionC2xTestWaitForMessage.md)
- **C2xTestWaitForSignalInRange**: [Waits for a Car2X message which has a signal that is inside or equals the given limits](Functions/CAPLfunctionC2xTestWaitForSignalInRange.md)
- **C2xTestWaitForSignalMatch**: [Waits for a Car2X message which has a signal that matches the given value.](Functions/CAPLfunctionC2xTestWaitForSignalMatch.md)

## General Functions

- **C2xGetDefaultMacId**: [Returns the MAC-ID of a WLAN interface.](Functions/CAPLfunctionC2xGetDefaultMacId.md)
- **C2xGetLastError**: [Gets the last error code.](Functions/CAPLfunctionC2xGetLastError.md)
- **C2xGetLastErrorText**: [Gets the description of the last error code.](Functions/CAPLfunctionC2xGetLastErrorText.md)
- **C2xRegisterCallback**: [Register a CAPL handler function.](Functions/CAPLfunctionC2xRegisterCallback.md)
- **C2xSetVerbosity**: [Sets the verbosity level of the Car2x IL.](Functions/CAPLfunctionC2xSetVerbosity.md)

## Packet API

- **C2xAddToken**: [Adds a token at the end of a protocol header.](Functions/CAPLfunctionC2xAddToken.md)
- **C2xCompletePacket**: [Completes a WLAN packet for sending.](Functions/CAPLfunctionC2xCompletePacket.md)
- **C2xGetMessageHandle**: [Get packet handle.](Functions/CAPLfunctionC2xGetMessageHandle.md)
- **C2xGetThisData**: [Gets the payload data of the highest interpretable protocol.](Functions/CAPLfunctionC2xGetThisData.md)
- **C2xGetThisMotorolaValue16**: [Gets received 16 bit value (Motorola format).](Functions/CAPLfunctionC2xGetThisMotorolaValue16.md)
- **C2xGetThisMotorolaValue32**: [Gets received 32 bit value (Motorola format).](Functions/CAPLfunctionC2xGetThisMotorolaValue32.md)
- **C2xGetThisMotorolaValue64**: [Gets received 64 bit value (Motorola format).](Functions/CAPLfunctionC2xGetThisMotorolaValue64.md)
- **C2xGetThisTimeNS**: [Gets time stamp of a received WLAN packet.](Functions/CAPLfunctionC2xGetThisTimeNS.md)
- **C2xGetThisValue8**: [Gets received 8 bit value.](Functions/CAPLfunctionC2xGetThisValue8.md)
- **C2xGetThisValue16**: [Gets received 16 bit value (Intel format).](Functions/CAPLfunctionC2xGetThisValue16.md)
- **C2xGetThisValue32**: [Gets received 32 bit value (Intel format).](Functions/CAPLfunctionC2xGetThisValue32.md)
- **C2xGetThisValue64**: [Gets received 64 bit value (Intel format).](Functions/CAPLfunctionC2xGetThisValue64.md)
- **C2xGetTokenBitOfBitString**: [Gets the value of a bit in a bit string.](Functions/CAPLfunctionC2xGetTokenBitOfBitString.md)
- **C2xGetTokenBitString**: [Gets the bit string value of a token.](Functions/CAPLfunctionC2xGetTokenBitString.md)
- **C2xGetTokenData**: [Gets the data of a token.](Functions/CAPLfunctionC2xGetTokenData.md)
- **C2xGetTokenInt**: [Gets the integer value of a token.](Functions/CAPLfunctionC2xGetTokenInt.md)
- **C2xGetTokenInt64**: [Gets the 64 bit integer value of a token.](Functions/CAPLfunctionC2xGetTokenInt64.md)
- **C2xGetTokenLengthBit**: [Gets the length of a token in bit.](Functions/CAPLfunctionC2xGetTokenLengthBit.md)
- **C2xGetTokenOidElement**: [Gets an element of the ASN.1 datatype OID.](Functions/CAPLfunctionC2xGetTokenOidElement.md)
- **C2xGetTokenPhys**: [Returns the physical value of the existing ASN.1 token in the packet](Functions/CAPLfunctionC2xGetTokenPhys.md)
- **C2xGetTokenString**: [Gets the string value of a token.](Functions/CAPLfunctionC2xGetTokenString.md)
- **C2xGetTokenSubString**: [Gets a part of a string value of a token.](Functions/CAPLfunctionC2xGetTokenSubString.md)
- **C2xInitPacket**: [Creates a new WLAN packet.](Functions/CAPLfunctionC2xInitPacket.md)
- **C2xInitProtocol**: [Initializes a protocol for a WLAN packet.](Functions/CAPLfunctionC2xInitProtocol.md)
- **C2xIsPacketValid**: [Checks if a WLAN packet has protocol errors.](Functions/CAPLfunctionC2xIsPacketValid.md)
- **C2xIsTokenAvailable**: [Checks if a token is part of a packet.](Functions/CAPLfunctionC2xIsTokenAvailable.md)
- **C2xOutputPacket**: [Sends a WLAN packet.](Functions/CAPLfunctionC2xOutputPacket.md)
- **C2xParsePacket**: [Reinterprets the packet after externally defined binary payload data has been assigned to the packet.](Functions/CAPLfunctionC2xParsePacket.md)
- **C2xReceivePacket**: [Registers a CAPL handler function to receive WLAN packets.](Functions/CAPLfunctionC2xReceivePacket.md)
- **C2xReleasePacket**: [Deletes a WLAN packet.](Functions/CAPLfunctionC2xReleasePacket.md)
- **C2xRemoveToken**: [Removes a token from a protocol header.](Functions/CAPLfunctionC2xRemoveToken.md)
- **C2xResizeToken**: [Modifies the length of a token.](Functions/CAPLfunctionC2xResizeToken.md)
- **C2xSetTokenBitOfBitString**: [Sets the value of a bit in a bit string.](Functions/CAPLfunctionC2xSetTokenBitOfBitString.md)
- **C2xSetTokenBitString**: [Sets the bit string value of a token.](Functions/CAPLfunctionC2xSetTokenBitString.md)
- **C2xSetTokenData**: [Sets the data of a token.](Functions/CAPLfunctionC2xSetTokenData.md)
- **C2xSetTokenInt**: [Sets the integer value of a token.](Functions/CAPLfunctionC2xSetTokenInt.md)
- **C2xSetTokenInt64**: [Sets the 64 bit integer value of a token.](Functions/CAPLfunctionC2xSetTokenInt64.md)
- **C2xSetTokenOidElement**: [Sets an element of the ASN.1 datatype OID.](Functions/CAPLfunctionC2xSetTokenOidElement.md)
- **C2xSetTokenPhys**: [Sets the physical value of the ASN.1 token in the packet.](Functions/CAPLfunctionC2xSetTokenPhys.md)
- **C2xSetTokenString**: [Sets the string value of a token.](Functions/CAPLfunctionC2xSetTokenString.md)

## Scenario API

- **C2xAdjustStationSpeedForCollision**: [Adjusts the speed of the given station for collision.](Functions/CAPLfunctionC2xAdjustStationSpeedForCollision.md)
- **C2xCreateStation**: [Creates a station and assigns it to the currently loaded scenario.](Functions/CAPLfunctionC2xCreateStation.md)
- **C2xGetNumberOfRoutePoints**: [Gets the number of points in route.](Functions/CAPLfunctionC2xGetNumberOfRoutePoints.md)
- **C2xGetReferencePoint**: [Gets position of reference point.](Functions/CAPLfunctionC2xGetReferencePoint.md)
- **C2xGetRoutePoint**: [Gets route point.](Functions/CAPLfunctionC2xGetRoutePoint.md)
- **C2xGetStationAttributeDouble**: [Returns the actual value of the floating point typed scenario attribute.](Functions/CAPLfunctionC2xGetStationAttributeDouble.md)
- **C2xGetStationAttributeInt64**: [Returns the actual value of the integer-typed scenario attribute.](Functions/CAPLfunctionC2xGetStationAttributeInt64.md)
- **C2xGetStationPosition**: [Returns the position and heading of a station as out parameters.](Functions/CAPLfunctionC2xGetStationPosition.md)
- **C2xGetStationPropertyDouble**: [Returns the value of a station property of type float that was assigned in a V2x scenario.](Functions/CAPLfunctionC2xGetStationPropertyDouble.md)
- **C2xGetStationPropertyInt64**: [Returns the value of a station property of type int64 that was assigned in a V2x scenario.](Functions/CAPLfunctionC2xGetStationPropertyInt64.md)
- **C2xGetStationSubAttributeDouble**: [Returns the actual value of the floating point typed scenario sub-attribute.](Functions/CAPLfunctionC2xGetStationSubAttributeDouble.md)
- **C2xGetStationSubAttributeInt64**: [Returns the actual value of the integer-typed scenario sub-attribute.](Functions/CAPLfunctionC2xGetStationSubAttributeInt64.md)
- **C2xIsScenarioStarted**: [Checks if the scenario assigned to the current CANoe DE product configuration is in the running state.](Functions/CAPLfunctionC2xIsScenarioStarted.md)
- **C2xLoadRoute**: [Loads route from a file.](Functions/CAPLfunctionC2xLoadRoute.md)
- **C2xLoadScenario**: [Loads the scenario from the file specified by a parameter.](Functions/CAPLfunctionC2xLoadScenario.md)
- **C2xMoveRouteRelativeToRefPoint**: [Moves a route relative to a reference point.](Functions/CAPLfunctionC2xMoveRouteRelativeToRefPoint.md)
- **C2xResetScenario**: [Resets the current scenario.](Functions/CAPLfunctionC2xResetScenario.md)
- **C2xSetRouteStartPoint**: [Sets start point on route to specified geographical position.](Functions/CAPLfunctionC2xSetRouteStartPoint.md)
- **C2xSetStationAttributeDouble**: [Sets an attribute value for a scenario station and a particular keypoint as double.](Functions/CAPLfunctionC2xSetStationAttributeDouble.md)
- **C2xSetStationAttributeInt64**: [Sets an attribute value for a scenario station and a particular keypoint as Int64.](Functions/CAPLfunctionC2xSetStationAttributeInt64.md)
- **C2xSetStationBaseAttributes**: [Assigns the data latitude, longitude, direction and speed to a dynamically added station of a scenario.](Functions/CAPLfunctionC2xSetStationBaseAttributes.md)
- **C2xSetStationOnRoute**: [Sets a specified station on a given route.](Functions/CAPLfunctionC2xSetStationOnRoute.md)
- **C2xSetStationsOnRoute**: [Sets stations on a given route.](Functions/CAPLfunctionC2xSetStationsOnRoute.md)
- **C2xSetStationSpeed**: [Changes the speed of a station.](Functions/CAPLfunctionC2xSetStationSpeed.md)
- **C2xSetStationStartOffset**: [Sets the station start offset.](Functions/CAPLfunctionC2xSetStationStartOffset.md)
- **C2xStartScenario**: [Starts the scenario assigned to the current CANoe DE product configuration immediately.](Functions/CAPLfunctionC2xStartScenario.md)
- **C2xStopScenario**: [Stops the scenario execution immediately.](Functions/CAPLfunctionC2xStopScenario.md)

## Security API

- **C2xSecCertificateCreate**: [Generate a certificate.](Functions/CAPLfunctionC2xSecCertificateCreate.md)
- **C2xSecCertificateGetHandle**: [Gets a certificate handle from a certificate.](Functions/CAPLfunctionC2xSecCertificateGetHandle.md)
- **C2xSecCertificateGetHashedId8**: [Gets HashedId8 digest of a certificate.](Functions/CAPLfunctionC2xSecCertificateGetHashedId8.md)
- **C2xSecCertificateGetName**: [Gets a certificate name.](Functions/CAPLfunctionC2xSecCertificateGetName.md)
- **C2xSecCertificateGetSignerHandle**: [Gets the signer (parent) certificate of a certificate.](Functions/CAPLfunctionC2xSecCertificateGetSignerHandle.md)
- **C2xSecCertificateGetSignerHashedId8**: [Gets the signer (parent) certificate’s HashedId8 digest.](Functions/CAPLfunctionC2xSecCertificateGetSignerHashedId8.md)
- **C2xSecCertificateGetStatus**: [Gets validity status of a certificate.](Functions/CAPLfunctionC2xSecCertificateGetStatus.md)
- **C2xSecCertificateValidAppSspBitmap**: [Validates the Service Specific Permission (SSP) bit mask of a certificate.](Functions/CAPLfunctionC2xSecCertificateValidAppSspBitmap.md)
- **C2xSecCertificateValidIdentifiedRegion**: [Validates the validity of a certificate region.](Functions/CAPLfunctionC2xSecCertificateValidIdentifiedRegion.md)
- **C2xSecPacketGetSignerHandle**: [Gets the handle of the certificate used by the signer of the packet.](Functions/CAPLfunctionC2xSecPacketGetSignerHandle.md)
- **C2xSecPacketGetSignerHashedId8**: [Gets the HashedId8 of the certificate used by the signer of the packet.](Functions/CAPLfunctionC2xSecPacketGetSignerHashedId8.md)
- **C2xSecPacketGetSignerType**: [Retrieves how the message signer information is included in the message.](Functions/CAPLfunctionC2xSecPacketGetSignerType.md)
- **C2xSecPacketGetStatus**: [Gets validity status of a packet.](Functions/CAPLfunctionC2xSecPacketGetStatus.md)
- **C2xSecPacketIsSecured**: [Check if a packet has a Security Layer.](Functions/CAPLfunctionC2xSecPacketIsSecured.md)
- **C2xSecPacketSetSignerHandle**: [Assigns a certificate to a Tx packet.](Functions/CAPLfunctionC2xSecPacketSetSignerHandle.md)
- **C2xSecPacketSetSignerType**: [Specifies how the message signer information is included in the message.](Functions/CAPLfunctionC2xSecPacketSetSignerType.md)

## Station API

- **C2xGetNodeName**: [Get the name of the station's assigned database node.](Functions/CAPLfunctionC2xGetNodeName.md)
- **C2xGetStationColor**: [Get the station's color.](Functions/CAPLfunctionC2xGetStationColor.md)
- **C2xGetStationHandle**: [Get the handle of an ITS Station.](Functions/CAPLfunctionC2xGetStationHandle.md)
- **C2xGetStationName**: [Get the station's name.](Functions/CAPLfunctionC2xGetStationName.md)
- **C2xAssignNodeToStation**: [Assigns a database node to an ITS station.](Functions/CAPLfunctionC2xAssignNodeToStation.md)
- **C2xGetStationHandleByStationName**: [Retrieves an ITS station handle by the name of the ITS station.](Functions/CAPLfunctionC2xGetStationHandleByStationName.md)
- **C2xRemoveNodeAssignment**: [Removes an assigned database node from an ITS station.](Functions/CAPLfunctionC2xRemoveNodeAssignment.md)

## Time API

- **C2xConvertMod32TsToUTC**: [A new CAPL function was implemented to convert a mod32 time stamp into a UTC time stamp as array of type long.](Functions/CAPLFunctionC2xConvertMod32TsToUTC.md)
- **C2xConvertTimeFromMSSinceUTC**: [Converts a time stamp in milliseconds since a reference time into a UTC time stamp.](Functions/CAPLfunctionC2xConvertTimeFromMSSinceUTC.md)
- **C2xConvertTimeToMSSinceUTC**: [Returns the elapsed milliseconds between a reference time and a time stamp.](Functions/CAPLfunctionC2xConvertTimeToMSSinceUTC.md)
- **C2xGetITSTimeStamp**: [Returns the time in milliseconds since 1.1.1970 00:00:00 to measurement start plus the simulation time.](Functions/CAPLfunctionC2xGetITSTimeStamp.md)

[Car2x Error Codes](CAPLfunctionsCar2xErrorCodes.md)
