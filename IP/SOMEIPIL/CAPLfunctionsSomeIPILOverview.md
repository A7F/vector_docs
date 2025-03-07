[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/CAPLfunctionsSomeIPILOverview.md)

**CAPL Functions** » **Ethernet** » **SOME/IP Interaction Layer**

# SOME/IP Interaction Layer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Ethernet**  
Only available with Option Ethernet.  
To use the CAPL functions the [SomeIP_IL.vmodule](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPInclude.md) must be included.

**ON THIS PAGE:**

- [Callback Functions](#Callback)
- [Client-Side API](#ClientSideAPI)
- [Control API](#ControlAPI)
- [Endpoints](#Endpoints)
- [General Functions](#General)
- [Low-level API](#LowLevelAPI)
- [Raw Data Access](#RawDataAccess)
- [Server-Side API](#ServerSideAPI)
- [Service Discovery](#ServiceDiscovery)
- [Static Configuration](#Static)
- [Symbolic Database Access](#SymDataAccess)
- [TCP Handling](#TCP)
- [Value Access](#ValueAccess)

## Callback Functions [▲ back](#Shortcuts)

- [<OnSomeIpEventReceived>](Functions/CAPLfunctionOnSomeIpEventReceived.md): CAPL handler to receive events.
- [<OnSomeIpFieldNotification>](Functions/CAPLfunctionOnSomeIpFieldNotification.md): CAPL handler to receive field change notifications.
- [<OnSomeIpMethodError>](Functions/CAPLfunctionOnSomeIpMethodError.md): A callback function with this signature must be passed to the CAPL function [SomeIpCreateMethodCall](Functions/CAPLfunctionSomeIpCreateMethodCall.md).
- [<OnSomeIpMethodRequest>](Functions/CAPLfunctionOnSomeIpMethodRequest.md): CAPL handler to request a method.
- [<OnSomeIpMethodResponse>](Functions/CAPLfunctionOnSomeIpMethodResponse.md): CAPL handler to response a method.
- [<OnSomeIpPrepareEvent>](Functions/CAPLfunctionOnSomeIpPrepareEvent.md): CAPL handler to prepare an event before sending.
- [OnSomeIpClientAepConnected](Functions/CAPLFunctionOnSomeIpClientAepConnected.md): This callback gets called when a client-side SOME/IP Application Endpoint gets connected to a remote peer.
- [OnSomeIpNewServerAep](Functions/CAPLFunctionOnSomeIpNewServerAep.md): This callback gets called when a server-side SOME/IP Application Endpoint gets opened.
- [OnSomeIpClosedIPv6TCPConnection](Functions/CAPLfunctionOnSomeIpClosedIPv6TCPConnection.md): CAPL handler to be called after a IL’s TCP connection has been closed
- [OnSomeIpEstablishedIPv6TCPConnection](Functions/CAPLfunctionOnSomeIpEstablishedIPv6TCPConnection.md): CAPL handler to be called after an incoming or outgoing TCP connection.
- [OnSomeIpClosedTLSConnection](Functions/CAPLfunctionOnSomeIpClosedTLSConnection.md): This callback will be called after a (D)TLS connection between the local endpoint and remote endpoint has been closed and it indicates whether the connection was closed by peer.
- [OnSomeIpEstablishedTLSConnection](Functions/CAPLfunctionOnSomeIpEstablishedTLSConnection.md): This callback will be called after a (D)TLS connection between the local endpoint and remote endpoint has been established.
- [OnSomeIpMessage](Functions/CAPLfunctionOnSomeIpMessage.md): CAPL handler to receive SOME/IP messages.
- [OnSomeIpProcessRxMessage](Functions/CAPLfunctionOnSomeIpProcessRxMessage.md): CAPL handler to be called when the IL has received a SOME/IP message.
- [OnSomeIpProcessTxMessage](Functions/CAPLfunctionOnSomeIpProcessTxMessage.md): CAPL handler to be called when the IL wants to send a SOME/IP message.
- [OnSomeIpSDClientEventGroupStatusChanged](Functions/CAPLfunctionOnSomeIpSDClientEventGroupStatusChanged.md): CAPL handler to be called when the status of an Event Group changes.
- [OnSomeIpSDClientServiceStatusChanged](Functions/CAPLfunctionOnSomeIpSDClientServiceStatusChanged.md): CAPL handler to be called when the status of a service changes.
- [OnSomeIpSDServerEventGroupStatusChanged](Functions/CAPLfunctionOnSomeIpSDServerEventGroupStatusChanged.md): CAPL handler to be called when a Client executes the Require Service or Release Service.
- [OnSomeIpSDServerEventGroupStatusChangedIPv6](Functions/CAPLfunctionOnSomeIpSDServerEventGroupStatusChanged.md): CAPL handler to be called when a Client executes the Require Service or Release Service.

## Client-Side API [▲ back](#Shortcuts)

- [SomeIpAddConsumedEventGroup](Functions/CAPLfunctionSomeIpAddConsumedEventGroup.md): Adds an Event Group to a Consumed Service Instance
- [SomeIpCallMethod](Functions/CAPLfunctionSomeIpCallMethod.md): Sends a request to the server.
- [SomeIpCreateConsumedServiceInstance](Functions/CAPLfunctionSomeIpCreateConsumedServiceInstance.md): Creates a Consumed Service Instance.
- [SomeIpCreateEventConsumer](Functions/CAPLfunctionSomeIpCreateEventConsumer.md): Adds an Event Consumer to a Consumed Service Instance.
- [SomeIpCreateFieldConsumer](Functions/CAPLfunctionSomeIpCreateFieldConsumer.md): Adds a Field Consumer to a Consumed Service Instance.
- [SomeIpCreateMethodCall](Functions/CAPLfunctionSomeIpCreateMethodCall.md): Creates a method call.
- [SomeIpReleaseConsumedServiceInstance](Functions/CAPLfunctionSomeIpReleaseConsumedServiceInstance.md): Deletes a Consumed Service Instance.
- [SomeIpRemoveConsumedEventGroup](Functions/CAPLfunctionSomeIpRemoveConsumedEventGroup.md): Removes an Event Group.
- [SomeIpRemoveEventConsumer](Functions/CAPLfunctionSomeIpRemoveEventConsumer.md): Deletes an Event Consumer.
- [SomeIpRemoveFieldConsumer](Functions/CAPLfunctionSomeIpRemoveFieldConsumer.md): Deletes a Field Consumer.
- [SomeIpRemoveMethodCall](Functions/CAPLfunctionSomeIpRemoveMethodCall.md): Deletes a method call.

## Control API [▲ back](#Shortcuts)

- [SomeIpILControlGetStatus](Functions/CAPLfunctionSomeIpILControlGetStatus.md): Returns current status of SOME/IP IL.
- [SomeIpILControlInit](Functions/CAPLfunctionSomeIpILControlInit.md): Initializes the SOME/IP IL.
- [SomeIpILControlResume](Functions/CAPLfunctionSomeIpILControlResume.md): Starts to send periodic messages
- [SomeIpILControlStart](Functions/CAPLfunctionSomeIpILControlStart.md): Starts the SOME/IP IL.
- [SomeIpILControlStop](Functions/CAPLfunctionSomeIpILControlStop.md): Stops the SOME/IP IL.
- [SomeIpILControlWait](Functions/CAPLfunctionSomeIpILControlWait.md): Stops sending cyclic messages.

## Endpoints [▲ back](#Shortcuts)

- [SomeIpCloseLocalApplicationEndpoint](Functions/CAPLfunctionSomeIpCloseLocalApplicationEndpoint.md): Closes an application endpoint.
- [SomeIpOpenLocalApplicationEndpoint](Functions/CAPLfunctionSomeIpOpenLocalApplicationEndpoint.md): Opens an endpoint for SOME/IP.
- [SomeIpTlsAuthenticateAsServerWithConfiguration](Functions/CAPLFunctionSomeIpTlsAuthenticateAsServerWithConfiguration.md): Starts the (D)TLS authentication handshake as server.
- [SomeIpTlsAuthenticateAsClientWithConfiguration](Functions/CAPLFunctionSomeIpTlsAuthenticateAsClientWithConfiguration.md): Starts the (D)TLS authentication handshake as client.

## General Functions [▲ back](#Shortcuts)

- [SomeIpGetLastError](Functions/CAPLfunctionSomeIpGetLastError.md): Interface to retrieve the last error which occurs in the SOME/IP IL.
- [SomeIpGetLastErrorText](Functions/CAPLfunctionSomeIpGetLastErrorText.md): Interface to retrieve the last error that occurred in the SOME/IP IL as string.
- [SomeIpGetSecurityValidationState](Functions/CAPLfunctionSomeIpGetSecurityValidationState.md): Returns the Security-Validation-State of a received SOME/IP message.
- [SomeIpSetProperty](Functions/CAPLfunctionSomeIpSetProperty.md): Sets a property of the SOME/IP IL.
- [SomeIpSetVerbosity](Functions/CAPLfunctionSomeIpSetVerbosity.md): Sets the verbosity level of the SOME/IP IL.

## Low-level API [▲ back](#Shortcuts)

- [SomeIpCreateMessage](Functions/CAPLfunctionSomeIpCreateMessage.md): Creates a SOME/IP message.
- [SomeIpOutputMessage](Functions/CAPLfunctionSomeIpOutputMessage.md): Sends a SOME/IP message.
- [SomeIpPostMessage](Functions/CAPLfunctionSomeIpPostMessage.md): Posts a SOME/IP message.
- [SomeIpReleaseMessage](Functions/CAPLfunctionSomeIpReleaseMessage.md): Deletes a SOME/IP message.

## Raw Data Access [▲ back](#Shortcuts)

- [SomeIpGetData](Functions/CAPLfunctionSomeIpGetData.md): Queries the raw data of a SOME/IP message.
- [SomeIpSerializeMessage](Functions/CAPLfunctionSomeIpSerializeMessage.md): Serializes the SOME/IP message including the header into a buffer.
- [SomeIpSetData](Functions/CAPLfunctionSomeIpSetData.md): Sets the raw data of a SOME/IP message.

## Server-Side API [▲ back](#Shortcuts)

- [SomeIpAddEvent](Functions/CAPLfunctionSomeIpAddEvent.md): Adds an event to a Provided Service Instance.
- [SomeIpAddEventToEventgroup](Functions/CAPLfunctionSomeIpAddEventToEventgroup.md): Assigns an event to an Event Group.
- [SomeIpAddField](Functions/CAPLfunctionSomeIpAddField.md): Adds a Field to a Provided Service Instance.
- [SomeIpAddFieldToEventgroup](Functions/CAPLfunctionSomeIpAddFieldToEventgroup.md): Assigns a Field to an Event Group.
- [SomeIpAddMethod](Functions/CAPLfunctionSomeIpAddMethod.md): Adds a method to a Provided Service Instance.
- [SomeIpAddProvidedEventGroup](Functions/CAPLfunctionSomeIpAddProvidedEventGroup.md): Adds an Event Group to a Provided Service Instance.
- [SomeIpCommitField](Functions/CAPLfunctionSomeIpCommitField.md): Commit field changes and send a field notification.
- [SomeIpCreateProvidedServiceInstance](Functions/CAPLfunctionSomeIpCreateProvidedServiceInstance.md): Creates a Provided Service Instance.
- [SomeIpReleaseProvidedServiceInstance](Functions/CAPLfunctionSomeIpReleaseProvidedServiceInstance.md): Deletes a Provided Service Instance.
- [SomeIpRemoveEvent](Functions/CAPLfunctionSomeIpRemoveEvent.md): Removes an event from a Provided Service Instance.
- [SomeIpRemoveEventFromEventgroup](Functions/CAPLfunctionSomeIpRemoveEventFromEventgroup.md): Removes an event from an Event Group.
- [SomeIpRemoveField](Functions/CAPLfunctionSomeIpRemoveField.md): Removes a field from a Provided Service Instance.
- [SomeIpRemoveFieldFromEventgroup](Functions/CAPLfunctionSomeIpRemoveFieldFromEventgroup.md): Removes a Field from an Event Group.
- [SomeIpRemoveMethod](Functions/CAPLfunctionSomeIpRemoveMethod.md): Removes a method from a Provided Service Instance.
- [SomeIpRemoveProvidedEventGroup](Functions/CAPLfunctionSomeIpRemoveProvidedEventGroup.md): Removes an Event Group from a Provided Service Instance.
- [SomeIpTriggerEvent](Functions/CAPLfunctionSomeIpTriggerEvent.md): Triggers sending of an event.

## Service Discovery [▲ back](#Shortcuts)

- [SomeIpSDDesubscribeEventGroup](Functions/CAPLfunctionSomeIpSDDesubscribeEventGroup.md): Informs the Remote-SD that Event Group is no longer needed.
- [SomeIpSDReleaseService](Functions/CAPLfunctionSomeIpSDReleaseService.md): Informs the local SD that the Remote Service is no longer needed.
- [SomeIpSDRequireService](Functions/CAPLfunctionSomeIpSDRequireService.md): Informs the local SD that the Remote Service is needed.
- [SomeIpSDSetServiceStatus](Functions/CAPLfunctionSomeIpSDSetServiceStatus.md): Informs the Service Discovery of the current status of a provided Service Instance.
- [SomeIpSDSubscribeEventGroup](Functions/CAPLfunctionSomeIpSDSubscribeEventGroup.md): Sends a Subscribe message.

## Static Configuration [▲ back](#Shortcuts)

- [SomeIpProvidedEventGroupAddConsumer](Functions/CAPLfunctionSomeIpProvidedEventGroupAddConsumer.md): Adds a consumer to a provided event group
- [SomeIpProvidedEventGroupRemoveConsumer](Functions/CAPLfunctionSomeIpProvidedEventGroupRemoveConsumer.md): Removes a consumer from a provided event group
- [SomeIpProvidedEventsAndFieldsAddConsumer](Functions/CAPLfunctionSomeIpProvidedEventsAndFieldsAddConsumer.md): Adds a consumer to a provided service instance
- [SomeIpProvidedEventsAndFieldsRemoveConsumer](Functions/CAPLfunctionSomeIpProvidedEventsAndFieldsRemoveConsumer.md): Removes a consumer from a provided service instance
- [SomeIpProvidedEventAddConsumer](Functions/CAPLfunctionSomeIpProvidedEventAddConsumer.md): Adds a consumer to a provided event
- [SomeIpProvidedEventRemoveConsumer](Functions/CAPLfunctionSomeIpProvidedEventRemoveConsumer.md): Removes a consumer from a provided event
- [SomeIpProvidedFieldAddConsumer](Functions/CAPLfunctionSomeIpProvidedFieldAddConsumer.md): Adds a consumer to a provided field
- [SomeIpProvidedFieldRemoveConsumer](Functions/CAPLfunctionSomeIpProvidedFieldRemoveConsumer.md): Removes a consumer from a provided field
- [SomeIpSetMulticastReceiverEndpoints](Functions/CAPLfunctionSomeIpSetMulticastReceiverEndpoints.md): Sets the multicast endpoint of a consumed event group
- [SomeIpSetProviderEndpoints](Functions/CAPLfunctionSomeIpSetProviderEndpoints.md): Sets the remote endpoints of a consumed service instance

## Symbolic Database Access [▲ back](#Shortcuts)

- [SomeIpGetConsumedObjectHandle](Functions/CAPLfunctionSomeIpGetConsumedObjectHandle.md): Enables to search for a consumed object which has been created separately.
- [SomeIpGetProvidedObjectHandle](Functions/CAPLfunctionSomeIpGetProvidedObjectHandle.md): Enables to search for a provided object which has been created separately.
- [SomeIpRegisterCallback](Functions/CAPLfunctionSomeIpRegisterCallback.md): Enables to register/unregister a CAPL callback function for an object which has been created separately.

## TCP Handling [▲ back](#Shortcuts)

- [SomeIpCloseEstablishedTCPConnection](Functions/CAPLfunctionSomeIpCloseEstablishedTCPConnection.md): Closes one or multiple database defined TCP connection(s).
- [SomeIpEstablishTCPConnection](Functions/CAPLfunctionSomeIpEstablishTCPConnection.md): Establishes one or multiple database defined TCP connection(s).
- [SomeIpTCPListen](Functions/CAPLfunctionSomeIpTCPListen.md): Listen on application endpoint

## Value Access [▲ back](#Shortcuts)

- [SomeIpFillValues](Functions/CAPLfunctionSomeIpFillValues.md): Fills the fields of SOME/IP events, methods and fields with increasing values for test purposes.
- [SomeIpGetDestinationAddress](Functions/CAPLfunctionSomeIpGetDestinationAddress.md): Returns the IPv4 destination address.
- [SomeIpGetDestinationPort](Functions/CAPLfunctionSomeIpGetDestinationPort.md): Returns the destination port (UDP/TCP).
- [SomeIpGetInterfaceVersion](Functions/CAPLfunctionSomeIpGetInterfaceVersion.md): Returns the Interface Version from the SOME/IP header.
- [SomeIpGetLength](Functions/CAPLfunctionSomeIpGetLength.md): Returns the length in bytes that is in the SOME/IP header.
- [SomeIpGetMessageId](Functions/CAPLfunctionSomeIpGetMessageId.md): Returns the Message ID from the SOME/IP header.
- [SomeIpGetMessageType](Functions/CAPLfunctionSomeIpGetMessageType.md): Returns the Message Type from the SOME/IP header.
- [SomeIpGetProtocol](Functions/CAPLfunctionSomeIpGetProtocol.md): Returns the protocol (UDP/TCP) the SOME/IP message was transmitted with.
- [SomeIpGetProtocolVersion](Functions/CAPLfunctionSomeIpGetProtocolVersion.md): Returns the Protocol Version from the SOME/IP header.
- [SomeIpGetRequestId](Functions/CAPLfunctionSomeIpGetRequestId.md): Returns the Request ID from the SOME/IP header.
- [SomeIpGetReturnCode](Functions/CAPLfunctionSomeIpGetReturnCode.md): Returns the Return Code from the SOME/IP header.
- [SomeIpGetSourceAddress](Functions/CAPLfunctionSomeIpGetSourceAddress.md): Returns the IPv4 sender address.
- [SomeIpGetSourcePort](Functions/CAPLfunctionSomeIpGetSourcePort.md): Returns the Source Port (UDP/TCP).
- [SomeIpGetValueDWord](Functions/CAPLfunctionSomeIpGetValueDWord.md): Gets the parameters of a SOME/IP message.
- [SomeIpGetValueFloat](Functions/CAPLfunctionSomeIpGetValueFloat.md): Gets the parameters of a SOME/IP message.
- [SomeIpGetValueInt64](Functions/CAPLfunctionSomeIpGetValueInt64.md): Gets the parameters of a SOME/IP message.
- [SomeIpGetValueLong](Functions/CAPLfunctionSomeIpGetValueLong.md): Gets the parameters of a SOME/IP message.
- [SomeIpGetValuePhys](Functions/CAPLfunctionSomeIpGetValuePhys.md): Gets the physical parameters of a SOME/IP message.
- [SomeIpGetValueQWord](Functions/CAPLfunctionSomeIpGetValueQWord.md): Gets the parameters of a SOME/IP message.
- [SomeIpGetValueString](Functions/CAPLfunctionSomeIpGetValueString.md): Gets the string parameters of a SOME/IP message.
- [SomeIpIsOptional](Functions/CAPLfunctionSomeIpIsOptional.md): Reads out if a parameter or member of the object is optional or mandatory.
- [SomeIpRemoveValue](Functions/CAPLfunctionSomeIpRemoveValue.md): Removes the parameters of a SOME/IP message.
- [SomeIpSetRequestId](Functions/CAPLfunctionSomeIpSetRequestId.md): Sets the Request ID.
- [SomeIpSetReturnCode](Functions/CAPLfunctionSomeIpSetReturnCode.md): Sets the return code.
- [SomeIpSetValueDWord](Functions/CAPLfunctionSomeIpSetValueDWord.md): Sets the parameters of a SOME/IP message.
- [SomeIpSetValueFloat](Functions/CAPLfunctionSomeIpSetValueFloat.md): Sets the parameters of a SOME/IP message.
- [SomeIpSetValueInt64](Functions/CAPLfunctionSomeIpSetValueInt64.md): Sets the parameters of a SOME/IP message.
- [SomeIpSetValueLong](Functions/CAPLfunctionSomeIpSetValueLong.md): Sets the parameters of a SOME/IP message.
- [SomeIpSetValuePhys](Functions/CAPLfunctionSomeIpSetValuePhys.md): Sets the physical parameters of a SOME/IP message.
- [SomeIpSetValueQWord](Functions/CAPLfunctionSomeIpSetValueQWord.md): Sets the parameters of a SOME/IP message.
- [SomeIpSetValueString](Functions/CAPLfunctionSomeIpSetValueString.md): Sets the string parameters of a SOME/IP message.

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)