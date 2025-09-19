# Communication Objects CAPL Functions (obsolete)

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

**ON THIS PAGE:**

- [Event Procedures](#EventProcedures)
- [Functions](#Functions)
- [Methods](#Methods)
- [Objects](#Objects)

## [Event Procedures](../../Shared/CAPL/General/EventProceduresOverview.md) 

- [on Abstract_EventSubscribed](EventProcedures/CAPLfunctionOnAbstractEventSubscribed.md): Is called when an event is subscribed at a provider.
- [on Abstract_EventUnsubscribed](EventProcedures/CAPLfunctionOnAbstractEventUnsubscribed.md): Is called when an event is unsubscribed at a provider.
- [on Abstract_FieldSubscribed](EventProcedures/CAPLfunctionOnAbstractFieldSubscribed.md): Is called when a field is subscribed at a provider.
- [on Abstract_FieldUnsubscribed](EventProcedures/CAPLfunctionOnAbstractFieldUnsubscribed.md): Is called when a field is unsubscribed at a provider.
- [on fct_Called](EventProcedures/CAPLfunctionOnfctCalled.md): Is called when a service function is called.
- [on fct_Calling](EventProcedures/CAPLfunctionOnfctCalling.md): Is called when a service function is about to be called.
- [on fct_Returned](EventProcedures/CAPLfunctionOnfctReturned.md): Is called when a service function answer is returned to the consumer.
- [on fct_Returning](EventProcedures/CAPLfunctionOnfctReturning.md): Is called when a service function is about to return its answer.
- [on PDU_change](EventProcedures/CAPLfunctionOnPDUChange.md): Is called when a PDU (of the new communication concept) is changed.
- [on PDU_Subscribed](EventProcedures/CAPLfunctionOnPDUSubscribed.md): Is called when a PDU is subscribed at a provider.
- [on PDU_Unsubscribed](EventProcedures/CAPLfunctionOnPDUUnsubscribed.md): Is called when a PDU is unsubscribed at a provider.
- [on PDU_update](EventProcedures/CAPLfunctionOnPDUUpdate.md): Is called when a PDU (of the new communication concept) is updated.
- [on SD_connection_established](EventProcedures/CAPLfunctionOnSDConnectionEstablished.md): Is called when a connection is established.
- [on SD_connection_failed](EventProcedures/CAPLfunctionOnSDConnectionFailed.md): Is called when a connection attempt fails.
- [on SD_connection_requested](EventProcedures/CAPLfunctionOnSDConnectionRequested.md): Is called when a connection is requested by a consumer.
- [on SD_consumer_discovered](EventProcedures/CAPLfunctionOnSDConsumerDiscovered.md): Is called when a new consumer is discovered.
- [on SD_provider_discovered](EventProcedures/CAPLfunctionOnSDProviderDiscovered.md): Is called when a new provider is discovered.
- [on SD_service_discovery](EventProcedures/CAPLfunctionOnSDServiceDiscovery.md): Is called when a new consumer is discovered.
- [on SOMEIP_EventGroupSubscribed](EventProcedures/CAPLfunctionOnSOMEIPEventGroupSubscribed.md): Is called when an event group is subscribed at a provider.
- [on SOMEIP_EventGroupUnsubscribed](EventProcedures/CAPLfunctionOnSOMEIPEventGroupUnsubscribed.md): Is called when an event group is unsubscribed at a provider.
- [on SOMEIP_EventGroupSubscribedConsumerSide](EventProcedures/CAPLfunctionOnSOMEIPEventGroupSubscribedConsumerSide.md): Is called on consumer side when a service provider has acknowledged the subscription for an event group.
- [on value_change](EventProcedures/CAPLfunctionOnValueChange.md): Is called when a communication object value changes.
- [on value_update](EventProcedures/CAPLfunctionOnValueUpdate.md): Is called when a communication object value is updated.

## Functions 

- [Abstract_CreateAddress](Functions/CAPLfunctionAbstractCreateAddress.md): Creates a pseudo-address for abstract binding.
- [Abstract_GetConsumerId](Functions/CAPLfunctionAbstractGetConsumerId.md): Gets an Id for a consumer with an abstract binding pseudo-address.
- [Abstract_GetDisplayName](Functions/CAPLfunctionAbstractGetDisplayName.md): Gets a display name for an endpoint with an abstract binding pseudo-address.
- [Abstract_GetProviderId](Functions/CAPLfunctionAbstractGetProviderId.md): Gets an Id for a provider with an abstract binding pseudo-address.
- [Abstract_ReleaseAddress](Functions/CAPLfunctionAbstractReleaseAddress.md): Releases a pseudo-address for abstract binding, freeing resources.
- [Abstract_SubscribeEvent](Functions/CAPLfunctionAbstractSubscribeEvent.md): Subscribes for a service event if abstract binding is used.
- [Abstract_SubscribeField](Functions/CAPLfunctionAbstractSubscribeField.md): Subscribes for a service field if abstract binding is used.
- [Abstract_SubscribePdu](Functions/CAPLfunctionAbstractSubscribePdu.md): Subscribes for a service PDU if abstract binding is used.
- [Abstract_UnsubscribeEvent](Functions/CAPLfunctionAbstractUnsubscribeEvent.md): Unsubscribes for a service event if abstract binding is used.
- [Abstract_UnsubscribeField](Functions/CAPLfunctionAbstractUnsubscribeField.md): Unsubscribes for a service field if abstract binding is used.
- [Abstract_UnsubscribePdu](Functions/CAPLfunctionAbstractUnsubscribePdu.md): Unsubscribes for a service PDU if abstract binding is used.
- [GetNrOfCOConsumers](Functions/CAPLfunctionGetNrOfCOConsumers.md): Gets the number of consumers at the communication object.
- [GetNrOfCOProviders](Functions/CAPLfunctionGetNrOfCOProviders.md): Gets the number of providers at the communication object.
- [GetNrOfCOReceivers](Functions/CAPLfunctionGetNrOfCOReceivers.md): Gets the number of receivers at the communication object.
- [GetNrOfCOSenders](Functions/CAPLfunctionGetNrOfCOSenders.md): Gets the number of senders at the communication object.
- [LookupConsumedEvent](Functions/CAPLfunctionLookupConsumedEvent.md): Searches for the specified consumed event.
- [LookupConsumedField](Functions/CAPLfunctionLookupConsumedField.md): Searches for the specified consumed field.
- [LookupConsumedMethod](Functions/CAPLfunctionLookupConsumedMethod.md): Searches for the specified consumed method.
- [LookupConsumedPDU](Functions/CAPLfunctionLookupConsumedPDU.md): Searches for the specified consumed PDU.
- [LookupConsumedService](Functions/CAPLfunctionLookupConsumedService.md): Searches for the specified consumed service.
- [LookupEventConsumer](Functions/CAPLfunctionLookupEventConsumer.md): Searches for the specified event consumer.
- [LookupEventProvider](Functions/CAPLfunctionLookupEventProvider.md): Searches for the specified event provider.
- [LookupFieldConsumer](Functions/CAPLfunctionLookupFieldConsumer.md): Searches for the specified field consumer.
- [LookupFieldProvider](Functions/CAPLfunctionLookupFieldProvider.md): Searches for the specified field provider.
- [LookupMeasuredEvent](Functions/CAPLfunctionLookupMeasuredEvent.md): Searches for the specified measured event.
- [LookupMeasuredField](Functions/CAPLfunctionLookupMeasuredField.md): Searches for the specified measured field.
- [LookupMeasuredMethod](Functions/CAPLfunctionLookupMeasuredMethod.md): Searches for the specified measured method.
- [LookupMeasuredPDU](Functions/CAPLfunctionLookupMeasuredPDU.md): Searches for the specified measured PDU.
- [LookupMeasuredService](Functions/CAPLfunctionLookupMeasuredService.md): Searches for the specified measured service.
- [LookupPDUConsumer](Functions/CAPLfunctionLookupPDUConsumer.md): Searches for the specified PDU consumer.
- [LookupPDUProvider](Functions/CAPLfunctionLookupPDUProvider.md): Searches for the specified PDU provider.
- [LookupProvidedEvent](Functions/CAPLfunctionLookupProvidedEvent.md): Searches for the specified provided event.
- [LookupProvidedField](Functions/CAPLfunctionLookupProvidedField.md): Searches for the specified provided field.
- [LookupProvidedMethod](Functions/CAPLfunctionLookupProvidedMethod.md): Searches for the specified provided method.
- [LookupProvidedPDU](Functions/CAPLfunctionLookupProvidedPDU.md): Searches for the specified provided PDU.
- [LookupProvidedService](Functions/CAPLfunctionLookupProvidedService.md): Searches for the specified provided service.
- [LookupRxPDU](Functions/CAPLfunctionLookupRxPDU.md): Searches for the specified rx PDU.
- [LookupRxSignal](Functions/CAPLfunctionLookupRxSignal.md): Searches for the specified rx signal.
- [LookupServiceConsumer](Functions/CAPLfunctionLookupServiceConsumer.md): Searches for the specified service consumer.
- [LookupServiceProvider](Functions/CAPLfunctionLookupServiceProvider.md): Searches for the specified service provider.
- [LookupTxPDU](Functions/CAPLfunctionLookupTxPDU.md): Searches for the specified tx PDU.
- [LookupTxSignal](Functions/CAPLfunctionLookupTxSignal.md): Searches for the specified tx signal.
- [SD_AddConsumer](Functions/CAPLfunctionSDAddConsumer.md): Dynamically adds a consumer endpoint to a service.
- [SD_AddProvider](Functions/CAPLfunctionSDAddProvider.md): Dynamically adds a provider endpoint to a service.
- [SD_AnnounceProvider](Functions/CAPLfunctionSDAnnounceProvider.md): Announces that a service provider is running.
- [SD_ConnectAsync](Functions/CAPLfunctionSDConnectAsync.md): Requests the establishment of a connection between a service provider and consumer.
- [SD_Disconnect](Functions/CAPLfunctionSDDisconnect.md): Disconnects a service provider and consumer.
- [SD_DiscoverProviders](Functions/CAPLfunctionSDDiscoverProviders.md): Discovers all running providers of a service in the role of a consumer.
- [SD_RemoveConsumer](Functions/CAPLfunctionSDRemoveConsumer.md): Dynamically removes a consumer endpoint from a service.
- [SD_RemoveProvider](Functions/CAPLfunctionSDRemoveProvider.md): Dynamically removes a provider endpoint from a service.
- [SD_SetAddress](Functions/CAPLfunctionSDSetAddress.md): Sets the address for a service endpoint.
- [SD_UnannounceProvider](Functions/CAPLfunctionSDUnannounceProvider.md): Announces that a service provider is no longer running.
- [SetSubscriptionStateIsolated](Functions/CAPLfunctionSetSubscriptionStateIsolated.md): Sets the subscription state for a service sub-member.
- [SOMEIP_ChangeServiceInstanceID](Functions/CAPLfunctionSOMEIPChangeServiceInstanceID.md): Changes the SOME/IP service instance ID of a provided service instance or the instance ID to which a consumed service should subscribe.
- [SOMEIP_InjectPDU](Functions/CAPLfunctionSOMEIPInjectPDU.md): Injects the PDU into the Communication Concepts SOME/IP-BindingBlock, where its then send.
- [SOMEIP_SubscribeEventGroup](Functions/CAPLfunctionSOMEIPSubscribeEventGroup.md): Subscribes for a service event group if SOME/IP binding is used.
- [SOMEIP_UnsubscribeEventGroup](Functions/CAPLfunctionSOMEIPUnsubscribeEventGroup.md): Unsubscribes for a service event group if SOME/IP binding is used.

**Test functions** see [Test Feature Set CAPL Functions](../Test/CAPLfunctionsTFSOverview.md#BMCommunicationConcept)

## Methods 

- [callcontext::CreatePermanentHandle](Methods/CAPLfunctionCallcontextCreatePermanentHandle.md): Creates a permanent handle for a call context.
- [callcontext::DeferAnswer](Methods/CAPLfunctionCallcontextDeferAnswer.md): Defers the answer for a function call indefinitely.
- [callcontext::FromHandle](Methods/CAPLfunctionCallcontextFromHandle.md): Retrieves a call context from a permanent handle.
- [callcontext::ReleaseHandle](Methods/CAPLfunctionCallcontextReleaseHandle.md): Releases a permanent handle for a call context.
- [callcontext::ReturnCall](Methods/CAPLfunctionCallcontextReturnCall.md): Returns the call, sending an answer.
- [callcontext::SetDefaultAnswer](Methods/CAPLfunctionCallcontextSetDefaultAnswer.md): Sets return value and out parameter values to defaults.
- [callcontext::SetTimeToAnswer](Methods/CAPLfunctionCallcontextSetTimeToAnswer.md): Defines the time until the call shall be returned.
- [consumedEventRef::AbstractIsEventRequested](Methods/CAPLfunctionConsumedEventRefAbstractIsEventRequested.md): Returns whether the specified event is currently requested.
- [consumedEventRef::AbstractReleaseEvent](Methods/CAPLfunctionConsumedEventRefAbstractReleaseEvent.md): Releases subscription of a specific event.
- [consumedEventRef::AbstractRequestEvent](Methods/CAPLfunctionConsumedEventRefAbstractRequestEvent.md): Requests subscription of a specific event.
- [consumedEventGroupRef::SOMEIPIsEventGroupRequested](Methods/CAPLfunctionConsumedEventGroupRefSOMEIPIsEventGroupRequested.md): Returns whether the specified event group is currently requested.
- [consumedEventGroupRef::SOMEIPReleaseEventGroup](Methods/CAPLfunctionConsumedEventGroupRefSOMEIPReleaseEventGroup.md): Releases subscription of a specific event group.
- [consumedEventGroupRef::SOMEIPRequestEventGroup](Methods/CAPLfunctionConsumedEventGroupRefSOMEIPRequestEventGroup.md): Requests subscription of a specific event group.
- [consumedFieldRef::AbstractIsFieldRequested](Methods/CAPLfunctionConsumedFieldRefAbstractIsFieldRequested.md): Returns whether the specified field is currently requested.
- [consumedFieldRef::AbstractReleaseField](Methods/CAPLfunctionConsumedFieldRefAbstractReleaseField.md): Releases subscription of a specific field.
- [consumedFieldRef::AbstractRequestField](Methods/CAPLfunctionConsumedFieldRefAbstractRequestField.md): Requests subscription of a specific field.
- [consumedMethodRef::CallAsync](Methods/CAPLfunctionConsumedMethodRefCallAsync.md): Calls a service method.
- [consumedMethodRef::CallAsyncPhys](Methods/CAPLfunctionConsumedMethodRefCallAsyncPhys.md): Calls a service method.
- [consumedPduRef::AbstractIsPduRequested](Methods/CAPLfunctionConsumedPduRefAbstractIsPduRequested.md): Returns whether the specified service PDU is currently requested.
- [Clear](Methods/CAPLfunctionClear.md): Clears the reference.
- [consumedPduRef::AbstractReleasePdu](Methods/CAPLfunctionConsumedPduRefAbstractReleasePdu.md): Releases subscription of a specific PDU.
- [consumedPduRef::AbstractRequestPdu](Methods/CAPLfunctionConsumedPduRefAbstractRequestPdu.md): Requests subscription of a specific PDU.
- [consumedServiceRef::IsServiceRequested](Methods/CAPLfunctionConsumedServiceRefIsServiceRequested.md): Returns whether the service is requested.
- [consumedServiceRef::ReleaseService](Methods/CAPLfunctionConsumedServiceRefReleaseService.md): Releases usage of a specific service.
- [consumedServiceRef::RequestService](Methods/CAPLfunctionConsumedServiceRefRequestService.md): Requests usage of a specific service.
- [eventProviderRef::GetNrOfSubscribedConsumers](Methods/CAPLfunctionEventProviderRefGetNrOfSubscribedConsumers.md): Returns the number of currently subscribed consumers.
- [eventProviderRef::GetSubscribedConsumer](Methods/CAPLfunctionEventProviderRefGetSubscribedConsumer.md): Returns a subscribed consumer.
- [eventProviderRef::Trigger](Methods/CAPLfunctionEventProviderRefTrigger.md): Triggers the specified event.
- [fieldProviderRef::GetNrOfSubscribedConsumers](Methods/CAPLfunctionfieldProviderRefGetNrOfSubscribedConsumers.md): Returns the number of currently subscribed consumers.
- [fieldProviderRef::GetSubscribedConsumer](Methods/CAPLfunctionfieldProviderRefGetSubscribedConsumer.md): Returns a subscribed consumer.
- [GetConsumedFieldRef](Methods/CAPLfunctionGetConsumedFieldRef.md): Returns the referred field.
- [GetConsumedServiceRef](Methods/CAPLfunctionGetConsumedServiceRef.md): Returns the referred service.
- [GetConsumer](Methods/CAPLfunctionGetConsumer.md): Returns the consumer participant.
- [GetConsumerIndex](Methods/CAPLfunctionGetConsumerIndex.md): Returns the consumer index.
- [GetProvidedFieldRef](Methods/CAPLfunctionGetProvidedFieldRef.md): Returns the referred field.
- [GetProvidedServiceRef](Methods/CAPLfunctionGetProvidedServiceRef.md): Returns the referred service.
- [GetProvider](Methods/CAPLfunctionGetProvider.md): Returns the provider participant.
- [GetProviderIndex](Methods/CAPLfunctionGetProviderIndex.md): Returns the provider index.
- [GetReceiver](Methods/CAPLfunctionGetReceiver.md): Returns the receiver participant.
- [GetReceiverIndex](Methods/CAPLfunctionGetReceiverIndex.md): Returns the receiver index.
- [GetSender](Methods/CAPLfunctionGetSender.md): Returns the sender participant.
- [GetSenderIndex](Methods/CAPLfunctionGetSenderIndex.md): Returns the sender index.
- [pduProviderRef::GetNrOfSubscribedConsumers](Methods/CAPLfunctionPduProviderRefGetNrOfSubscribedConsumers.md): Returns the number of currently subscribed consumers.
- [pduProviderRef::GetSubscribedConsumer](Methods/CAPLfunctionPduProviderRefGetSubscribedConsumer.md): Returns a subscribed consumer.
- [providedEventRef::Trigger](Methods/CAPLfunctionProvidedEventRefTrigger.md): Triggers the specified event.
- [serviceProviderRef::IsServiceProvided](Methods/CAPLfunctionServiceProviderRefIsServiceProvided.md): Returns whether the service is provided.
- [serviceProviderRef::ProvideService](Methods/CAPLfunctionServiceProviderRefProvideService.md): Provides the service at the endpoint.
- [serviceProviderRef::ReleaseService](Methods/CAPLfunctionServiceProviderRefReleaseService.md): Provides the service at the endpoint.
- [SetConsumer](Methods/CAPLfunctionSetConsumer.md): Set the consumer endpoint.
- [SetEvent](Methods/CAPLfunctionSetEvent.md): Sets the event.
- [SetField](Methods/CAPLfunctionSetField.md): Sets the field.
- [SetMethod](Methods/CAPLfunctionSetMethod.md): Sets the method.
- [SetPDU](Methods/CAPLfunctionSetPDU.md): Sets the PDU/referred PDU object.
- [SetProvider](Methods/CAPLfunctionSetProvider.md): Set the provider endpoint.
- [SetReceiver](Methods/CAPLfunctionSetReceiver.md): Set the receiver endpoint.
- [SetSender](Methods/CAPLfunctionSetSender.md): Set the sender endpoint.
- [SetService](Methods/CAPLfunctionSetService.md): Sets the service.
- [SetSignal](Methods/CAPLfunctionSetSignal.md): Sets the referred signal object.
- [valueHandle::ClearChangeFlag](Methods/CAPLfunctionValueClearChangeFlag.md): Clears the change flag of the value.
- [valueHandle::ClearUpdateFlag](Methods/CAPLfunctionValueClearUpdateFlag.md): Clears the update flag of the value.
- [valueHandle::GetChangeCount](Methods/CAPLfunctionValueGetChangeCount.md): Returns the change count of the value.
- [valueHandle::GetUpdateCount](Methods/CAPLfunctionValueGetUpdateCount.md): Returns the update count of the value.
- [valueHandle::GetValueState](Methods/CAPLfunctionValueGetValueState.md): Returns the state of the value.
- [valueHandle::ResetValueState](Methods/CAPLfunctionValueResetValueState.md): Resets the state of the value.

## Objects 

- [callContext](Objects/CAPLfunctionCallContext.md): Contains data of a function call.
- [consumedEventRef](Objects/CAPLfunctionConsumedEventRef.md): References a consumed event endpoint.
- [consumedFieldRef](Objects/CAPLfunctionConsumedFieldRef.md): References a consumed field endpoint.
- [consumedMethodRef](Objects/CAPLfunctionConsumedMethodRef.md): References a consumed method endpoint.
- [consumedPDURef](Objects/CAPLfunctionConsumedPDURef.md): References a consumed PDU endpoint.
- [consumedServiceRef](Objects/CAPLfunctionConsumedServiceRef.md): References a consumed service endpoint.
- [eventConsumerRef](Objects/CAPLfunctionEventConsumerRef.md): References an event consumer endpoint.
- [eventProviderRef](Objects/CAPLfunctionEventProviderRef.md): References an event provider endpoint.
- [fieldConsumerRef](Objects/CAPLfunctionFieldConsumerRef.md): References a field consumer endpoint.
- [fieldProviderRef](Objects/CAPLfunctionFieldProviderRef.md): References a field provider endpoint.
- [measuredEventRef](Objects/CAPLfunctionMeasuredEventRef.md): References an event measurement point.
- [measuredFieldRef](Objects/CAPLfunctionMeasuredFieldRef.md): References a field measurement point.
- [measuredMethodRef](Objects/CAPLfunctionMeasuredMethodRef.md): References a method measurement point.
- [measuredPDURef](Objects/CAPLfunctionMeasuredPDURef.md): References a PDU measurement point.
- [measuredServicePDURef](Objects/CAPLfunctionMeasuredServicePDURef.md): References a service PDU measurement point.
- [measuredServiceRef](Objects/CAPLfunctionMeasuredServiceRef.md): References a service measurement point.
- [pduConsumerRef](Objects/CAPLfunctionPDUConsumerRef.md): References a PDU consumer endpoint.
- [pduProviderRef](Objects/CAPLfunctionPDUProviderRef.md): References a PDU provider endpoint.
- [providedEventRef](Objects/CAPLfunctionProvidedEventRef.md): References a provided event endpoint.
- [providedFieldRef](Objects/CAPLfunctionProvidedFieldRef.md): References a provided field endpoint.
- [providedMethodRef](Objects/CAPLfunctionProvidedMethodRef.md): References a provided method endpoint.
- [providedPDURef](Objects/CAPLfunctionProvidedPDURef.md): References a provided PDU endpoint.
- [providedServiceRef](Objects/CAPLfunctionProvidedServiceRef.md): References a provided service endpoint.
- [rxPDURef](Objects/CAPLfunctionRxPDURef.md): References an rx PDU endpoint.
- [rxSignalRef](Objects/CAPLfunctionRxSignalRef.md): References an rx signal endpoint.
- [serviceConsumerRef](Objects/CAPLfunctionServiceConsumerRef.md): References a service consumer endpoint.
- [serviceProviderRef](Objects/CAPLfunctionServiceProviderRef.md): References a service provider endpoint.
- [txPDURef](Objects/CAPLfunctionTxPDURef.md): References a tx PDU endpoint.
- [txSignalRef](Objects/CAPLfunctionTxSignalRef.md): References a tx signal endpoint.

[Communication Concept](../../CANoeCANalyzer/CommunicationConcept/CC.md) • [Programming with Communication Concept](../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
