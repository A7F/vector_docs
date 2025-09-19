[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/CAPLfunctionsAREthILOverview.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Ethernet Interaction Layer**

# AUTOSAR Ethernet Interaction Layer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## ON THIS PAGE:

- [Callback Functions](#Callback)
- [Client-Side API](#ClientSideAPI)
- [Control API](#ControlAPI)
- [Endpoints](#Endpoints)
- [General Functions](#General)
- [Low-level API](#LowLevelAPI)
- [Raw Data Access](#RawDataAccess)
- [Server-Side API](#ServerSideAPI)
- [Service Discovery](#ServiceDiscovery)
- [Static Configuration](../SOMEIPIL/CAPLfunctionsSomeIPILOverview.md#Static)
- [Symbolic Database Access](#SymDataAccess)
- [TCP Handling](../SOMEIPIL/CAPLfunctionsSomeIPILOverview.md#TCP)
- [Value Access](#ValueAccess)

## Callback Functions [▲ back](#Shortcuts)

- [`<OnAREthEventReceived>`](Functions/CAPLfunctionOnAREthEventReceived.md): CAPL handler to receive events.
- [`<OnAREthFieldNotification>`](Functions/CAPLfunctionOnAREthFieldNotification.md): CAPL handler to receive field change notifications.
- [`<OnAREthMethodError>`](Functions/CAPLfunctionOnAREthMethodError.md): A callback function with this signature must be passed to the CAPL function [AREthCreateMethodCall](Functions/CAPLfunctionAREthCreateMethodCall.md).
- [`<OnAREthMethodRequest>`](Functions/CAPLfunctionOnAREthMethodRequest.md): CAPL handler to request a method.
- [`<OnAREthMethodResponse>`](Functions/CAPLfunctionOnAREthMethodResponse.md): CAPL handler to response a method.
- [`<OnAREthPrepareEvent>`](Functions/CAPLfunctionOnAREthPrepareEvent.md): CAPL handler to prepare an event before sending.
- [OnAREthClosedIPv6TCPConnection](Functions/CAPLfunctionOnAREthClosedIPv6TCPConnection.md): CAPL handler to be called after a IL’s TCP connection has been closed.
- [OnAREthEstablishedIPv6TCPConnection](Functions/CAPLfunctionOnAREthEstablishedIPv6TCPConnection.md): CAPL handler to be called after an incoming or outgoing TCP connection.
- [OnAREthClientAepConnected](Functions/CAPLFunctionOnAREthClientAepConnected.md): This callback gets called when a server-side SOME/IP Application Endpoint gets opened.
- [OnAREthClosedTLSConnection](Functions/CAPLfunctionOnAREthClosedTLSConnection.md): This callback will be called after a (D)TLS connection between the local endpoint and remote endpoint has been closed and it indicates whether the connection was closed by peer.
- [OnAREthEstablishedTLSConnection](Functions/CAPLfunctionOnAREthEstablishedTLSConnection.md): This callback will be called after a (D)TLS connection between the local endpoint and remote endpoint has been established.
- [OnAREthMessage](Functions/CAPLfunctionOnAREthMessage.md): CAPL handler to receive SOME/IP messages.
- [OnAREthNewServerAep](Functions/CAPLFunctionOnAREthNewServerAep.md): This callback gets called when a client-side SOME/IP Application Endpoint gets connected to a remote peer.
- [OnAREthProcessRxMessage](Functions/CAPLfunctionOnAREthProcessRxMessage.md): CAPL handler to be called when the IL has received a SOME/IP message.
- [OnAREthProcessTxARPDU](Functions/CAPLfunctionOnAREthProcessTxARPDU.md): Is called by the interaction layer before sending an AUTOSAR PDU.
- [OnAREthProcessTxMessage](Functions/CAPLfunctionOnAREthProcessTxMessage.md): CAPL handler to be called when the IL wants to send a SOME/IP message.
- [OnAREthSDClientEventGroupStatusChanged](Functions/CAPLfunctionOnAREthSDClientEventGroupStatusChanged.md): CAPL handler to be called when the status of an Event Group changes.
- [OnAREthSDClientServiceStatusChanged](Functions/CAPLfunctionOnAREthSDClientServiceStatusChanged.md): CAPL handler to be called when the status of a service changes.
- [OnAREthSDServerEventGroupStatusChanged](Functions/CAPLfunctionOnAREthSDServerEventGroupStatusChanged.md): CAPL handler to be called when a Client executes the Require Service or Release Service.
- [OnAREthSDServerEventGroupStatusChangedIPv6](Functions/CAPLfunctionOnAREthSDServerEventGroupStatusChangedIPv6.md): CAPL handler to be called when a Client executes the Require Service or Release Service.

## Client-Side API [▲ back](#Shortcuts)

- [AREthAddConsumedEventGroup](Functions/CAPLfunctionAREthAddConsumedEventGroup.md): Adds an Event Group to a Consumed Service Instance
- [AREthCallMethod](Functions/CAPLfunctionAREthCallMethod.md): Sends a request to the server.
- [AREthCreateConsumedServiceInstance](Functions/CAPLfunctionAREthCreateConsumedServiceInstance.md): Creates a Consumed Service Instance.
- [AREthCreateEventConsumer](Functions/CAPLfunctionAREthCreateEventConsumer.md): Adds an Event Consumer to a Consumed Service Instance.
- [AREthCreateFieldConsumer](Functions/CAPLfunctionAREthCreateFieldConsumer.md): Adds a Field Consumer to a Consumed Service Instance.
- [AREthCreateMethodCall](Functions/CAPLfunctionAREthCreateMethodCall.md): Creates a method call.
- [AREthReleaseConsumedServiceInstance](Functions/CAPLfunctionAREthReleaseConsumedServiceInstance.md): Deletes a Consumed Service Instance.
- [AREthRemoveConsumedEventGroup](Functions/CAPLfunctionAREthRemoveConsumedEventGroup.md): Removes an Event Group.
- [AREthRemoveEventConsumer](Functions/CAPLfunctionAREthRemoveEventConsumer.md): Deletes an Event Consumer.
- [AREthRemoveFieldConsumer](Functions/CAPLfunctionAREthRemoveFieldConsumer.md): Deletes a Field Consumer.
- [AREthRemoveMethodCall](Functions/CAPLfunctionAREthRemoveMethodCall.md): Deletes a method call.

## Control API [▲ back](#Shortcuts)

- [AREthILControlGetStatus](Functions/CAPLfunctionAREthILControlGetStatus.md): Returns current status of AUTOSAR Eth IL.
- [AREthILControlInit](Functions/CAPLfunctionAREthILControlInit.md): Initializes the AUTOSAR Eth IL.
- [AREthILControlResume](Functions/CAPLfunctionAREthILControlResume.md): Starts to send periodic messages
- [AREthILControlStart](Functions/CAPLfunctionAREthILControlStart.md): Starts the AUTOSAR Eth IL.
- [AREthILControlStop](Functions/CAPLfunctionAREthILControlStop.md): Stops the AUTOSAR Eth IL.
- [AREthILControlWait](Functions/CAPLfunctionAREthILControlWait.md): Stops sending cyclic messages.

## Endpoints [▲ back](#Shortcuts)

- [AREthCloseLocalApplicationEndpoint](Functions/CAPLfunctionAREthCloseLocalApplicationEndpoint.md): Closes an application endpoint.
- [AREthOpenLocalApplicationEndpoint](Functions/CAPLfunctionAREthOpenLocalApplicationEndpoint.md): Opens an application endpoint.
- [AREthTlsAuthenticateAsClientWithConfiguration](Functions/CAPLFunctionAREthTlsAuthenticateAsClientWithConfiguration.md): Starts the (D)TLS authentication handshake as client.
- [AREthTlsAuthenticateAsServerWithConfiguration](Functions/CAPLFunctionAREthTlsAuthenticateAsServerWithConfiguration.md): Starts the (D)TLS authentication handshake as server.
- [AREthPreConfigureTlsConnection](Functions/CAPLfunctionAREthPreConfigureTlsConnection.md): Preconfigures (D)TLS connection between localAEP and remoteAEP at measurement start.

## General Functions [▲ back](#Shortcuts)

- [AREthGetLastError](Functions/CAPLfunctionAREthGetLastError.md): Interface to retrieve the last error which occurs in the AUTOSAR Eth IL.
- [AREthGetLastErrorText](Functions/CAPLfunctionAREthGetLastErrorText.md): Interface to retrieve the last error that occurred in the AUTOSAR Eth IL as string.
- [AREthGetSecurityValidationState](Functions/CAPLfunctionAREthGetSecurityValidationState.md): Returns the Security-Validation-State of a received SOME/IP message.
- [AREthSetProperty](Functions/CAPLfunctionAREthSetProperty.md): Sets a property of the AUTOSAR Eth IL.
- [AREthSetVerbosity](Functions/CAPLfunctionAREthSetVerbosity.md): Sets the verbosity level of the AUTOSAR Eth IL.

## Low-level API [▲ back](#Shortcuts)

- [AREthCreateMessage](Functions/CAPLfunctionAREthCreateMessage.md): Creates a SOME/IP message.
- [AREthOutputMessage](Functions/CAPLfunctionAREthOutputMessage.md): Sends a SOME/IP message.
- [AREthPostMessage](Functions/CAPLfunctionAREthPostMessage.md): Posts a SOME/IP message.
- [AREthReleaseMessage](Functions/CAPLfunctionAREthReleaseMessage.md): Deletes a SOME/IP message.
- [AREthSendARPDUTo](Functions/CAPLfunctionAREthSendARPDUTo.md): Sends data as AUTOSAR PDU via a connection.

## Raw Data Access [▲ back](#Shortcuts)

- [AREthGetData](Functions/CAPLfunctionAREthGetData.md): Queries the raw data of a SOME/IP message.
- [AREthSerializeMessage](Functions/CAPLfunctionAREthSerializeMessage.md): Serializes the SOME/IP message including the header into a buffer.
- [AREthSetData](Functions/CAPLfunctionAREthSetData.md): Sets the raw data of a SOME/IP message.

## Server-Side API [▲ back](#Shortcuts)

- [AREthAddEvent](Functions/CAPLfunctionAREthAddEvent.md): Adds an event to a Provided Service Instance.
- [AREthAddEventToEventgroup](Functions/CAPLfunctionAREthAddEventToEventgroup.md): Assigns an event to an Event Group.
- [AREthAddField](Functions/CAPLfunctionAREthAddField.md): Adds a Field to a Provided Service Instance.
- [AREthAddFieldToEventgroup](Functions/CAPLfunctionAREthAddFieldToEventgroup.md): Assigns a Field to an Event Group.
- [AREthAddMethod](Functions/CAPLfunctionAREthAddMethod.md): Adds a method to a Provided Service Instance.
- [AREthAddProvidedEventGroup](Functions/CAPLfunctionAREthAddProvidedEventGroup.md): Adds an Event Group to a Provided Service Instance.
- [AREthCommitField](Functions/CAPLfunctionAREthCommitField.md): Commit field changes and send a field notification.
- [AREthCreateProvidedServiceInstance](Functions/CAPLfunctionAREthCreateProvidedServiceInstance.md): Creates a Provided Service Instance.
- [AREthReleaseProvidedServiceInstance](Functions/CAPLfunctionAREthReleaseProvidedServiceInstance.md): Deletes a Provided Service Instance.
- [AREthRemoveEvent](Functions/CAPLfunctionAREthRemoveEvent.md): Removes an event from a Provided Service Instance.
- [AREthRemoveEventFromEventgroup](Functions/CAPLfunctionAREthRemoveEventFromEventgroup.md): Removes an event from an Event Group.
- [AREthRemoveField](Functions/CAPLfunctionAREthRemoveField.md): Removes a field from a Provided Service Instance.
- [AREthRemoveFieldFromEventgroup](Functions/CAPLfunctionAREthRemoveFieldFromEventgroup.md): Removes a Field from an Event Group.
- [AREthRemoveMethod](Functions/CAPLfunctionAREthRemoveMethod.md): Removes a method from a Provided Service Instance.
- [AREthRemoveProvidedEventGroup](Functions/CAPLfunctionAREthRemoveProvidedEventGroup.md): Removes an Event Group from a Provided Service Instance.
- [AREthTriggerEvent](Functions/CAPLfunctionAREthTriggerEvent.md): Triggers sending of an event.

## Service Discovery [▲ back](#Shortcuts)

- [AREthSDDesubscribeEventGroup](Functions/CAPLfunctionAREthSDDesubscribeEventGroup.md): Informs the Remote-SD that Event Group is no longer needed.
- [AREthSDReleaseService](Functions/CAPLfunctionAREthSDReleaseService.md): Informs the local SD that the Remote Service is no longer needed.
- [AREthSDRequireService](Functions/CAPLfunctionAREthSDRequireService.md): Informs the local SD that the Remote Service is needed.
- [AREthSDSetServiceStatus](Functions/CAPLfunctionAREthSDSetServiceStatus.md): Informs the Service Discovery of the current status of a provided Service Instance.
- [AREthSDSubscribeEventGroup](Functions/CAPLfunctionAREthSDSubscribeEventGroup.md): Sends a Subscribe message.

## Static Configuration [▲ back](#Shortcuts)

- [AREthProvidedEventGroupAddConsumer](Functions/CAPLfunctionAREthProvidedEventGroupAddConsumer.md): Adds a consumer to a provided event group
- [AREthProvidedEventGroupRemoveConsumer](../SOMEIPIL/Functions/CAPLfunctionSomeIpProvidedEventGroupRemoveConsumer.md): Removes a consumer from a provided event group
- [AREthProvidedEventsAndFieldsAddConsumer](Functions/CAPLfunctionAREthProvidedEventsAndFieldsAddConsumer.md): Adds a consumer to a provided service instance
- [AREthProvidedEventsAndFieldsRemoveConsumer](Functions/CAPLfunctionAREthProvidedEventsAndFieldsRemoveConsumer.md): Removes a consumer from a provided service instance
- [AREthProvidedEventAddConsumer](Functions/CAPLfunctionAREthProvidedEventAddConsumer.md): Adds a consumer to a provided event
- [AREthProvidedEventRemoveConsumer](Functions/CAPLfunctionAREthProvidedEventRemoveConsumer.md): Removes a consumer from a provided event
- [AREthProvidedFieldAddConsumer](Functions/CAPLfunctionAREthProvidedFieldAddConsumer.md): Adds a consumer to a provided field
- [AREthProvidedFieldRemoveConsumer](Functions/CAPLfunctionAREthProvidedFieldRemoveConsumer.md): Removes a consumer from a provided field
- [AREthSetMulticastReceiverEndpoints](Functions/CAPLfunctionAREthSetMulticastReceiverEndpoints.md): Sets the multicast endpoint of a consumed event group
- [AREthSetProviderEndpoints](Functions/CAPLfunctionAREthSetProviderEndpoints.md): Sets the remote endpoints of a consumed service instance

## Symbolic Database Access [▲ back](#Shortcuts)

- [AREthGetConsumedObjectHandle](Functions/CAPLfunctionAREthGetConsumedObjectHandle.md): Enables to search for a consumed object which has been created separately.
- [AREthGetProvidedObjectHandle](Functions/CAPLfunctionAREthGetProvidedObjectHandle.md): Enables to search for a provided object which has been created separately.
- [AREthRegisterCallback](Functions/CAPLfunctionAREthRegisterCallback.md): Enables to register/unregister a CAPL callback function for an object which has been created separately.

## TCP Handling [▲ back](#Shortcuts)

- [AREthCloseEstablishedTCPConnection](Functions/CAPLfunctionAREthCloseEstablishedTCPConnection.md): Closes one or multiple database defined TCP connection(s).
- [AREthEstablishTCPConnection](Functions/CAPLfunctionAREthEstablishTCPConnection.md): Establishes one or multiple database defined TCP connection(s).
- [AREthTCPListen](Functions/CAPLfunctionAREthTCPListen.md): Listen on application endpoint

## Value Access [▲ back](#Shortcuts)

- [AREthFillValues](Functions/CAPLfunctionAREthFillValues.md): Fills the fields of SOME/IP events, methods and fields with increasing values for test purposes.
- [AREthGetDestinationAddress](Functions/CAPLfunctionAREthGetDestinationAddress.md): Returns the IPv4 destination address.
- [AREthGetDestinationPort](Functions/CAPLfunctionAREthGetDestinationPort.md): Returns the destination port (UDP/TCP).
- [AREthGetInterfaceVersion](Functions/CAPLfunctionAREthGetInterfaceVersion.md): Returns the Interface Version from the SOME/IP header.
- [AREthGetLength](Functions/CAPLfunctionAREthGetLength.md): Returns the length in bytes that is in the SOME/IP header.
- [AREthGetMessageId](Functions/CAPLfunctionAREthGetMessageId.md): Returns the Message ID from the SOME/IP header.
- [AREthGetMessageType](Functions/CAPLfunctionAREthGetMessageType.md): Returns the Message Type from the SOME/IP header.
- [AREthGetProtocol](Functions/CAPLfunctionAREthGetProtocol.md): Returns the protocol (UDP/TCP) the SOME/IP message was transmitted with.
- [AREthGetProtocolVersion](Functions/CAPLfunctionAREthGetProtocolVersion.md): Returns the Protocol Version from the SOME/IP header.
- [AREthGetRequestId](Functions/CAPLfunctionAREthGetRequestId.md): Returns the Request ID from the SOME/IP header.
- [AREthGetReturnCode](Functions/CAPLfunctionAREthGetReturnCode.md): Returns the Return Code from the SOME/IP header.
- [AREthGetSourceAddress](Functions/CAPLfunctionAREthGetSourceAddress.md): Returns the IPv4 sender address.
- [AREthGetSourcePort](Functions/CAPLfunctionAREthGetSourcePort.md): Returns the Source Port (UDP/TCP).
- [AREthGetValueDWord](Functions/CAPLfunctionAREthGetValueDWord.md): Gets the parameters of a SOME/IP message.
- [AREthGetValueFloat](Functions/CAPLfunctionAREthGetValueFloat.md): Gets the parameters of a SOME/IP message.
- [AREthGetValueInt64](Functions/CAPLfunctionAREthGetValueInt64.md): Gets the parameters of a SOME/IP message.
- [AREthGetValueLong](Functions/CAPLfunctionAREthGetValueLong.md): Gets the parameters of a SOME/IP message.
- [AREthGetValuePhys](Functions/CAPLfunctionAREthGetValuePhys.md): Gets the physical parameters of a SOME/IP message.
- [AREthGetValueQWord](Functions/CAPLfunctionAREthGetValueQWord.md): Gets the parameters of a SOME/IP message.
- [AREthGetValueString](Functions/CAPLfunctionAREthGetValueString.md): Gets the string parameters of a SOME/IP message.
- [AREthIsOptional](Functions/CAPLfunctionAREthIsOptional.md): Reads out if a parameter or member of the object is optional or mandatory.
- [AREthRemoveValue](Functions/CAPLfunctionAREthRemoveValue.md): Removes the parameters of a SOME/IP message.
- [AREthSetRequestId](Functions/CAPLfunctionAREthSetRequestId.md): Sets the Request ID.
- [AREthSetReturnCode](Functions/CAPLfunctionAREthSetReturnCode.md): Sets the return code.
- [AREthSetValueDWord](Functions/CAPLfunctionAREthSetValueDWord.md): Sets the parameters of a SOME/IP message.
- [AREthSetValueFloat](Functions/CAPLfunctionAREthSetValueFloat.md): Sets the parameters of a SOME/IP message.
- [AREthSetValueInt64](Functions/CAPLfunctionAREthSetValueInt64.md): Sets the parameters of a SOME/IP message.
- [AREthSetValueLong](Functions/CAPLfunctionAREthSetValueLong.md): Sets the parameters of a SOME/IP message.
- [AREthSetValuePhys](Functions/CAPLfunctionAREthSetValuePhys.md): Sets the physical parameters of a SOME/IP message.
- [AREthSetValueQWord](Functions/CAPLfunctionAREthSetValueQWord.md): Sets the parameters of a SOME/IP message.
- [AREthSetValueString](Functions/CAPLfunctionAREthSetValueString.md): Sets the string parameters of a SOME/IP message.

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
