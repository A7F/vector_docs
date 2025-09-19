# Distributed Objects CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

## Distributed Objects

Overview of objects and methods to work with distributed objects.

---

**ON THIS PAGE:**

- [Event Procedures](#EventProcedures)
- [Functions](#Functions)
- [Methods](#Methods)
- [Objects](#Objects)

## Event Procedures 

- [on any_fct_called](EventProcedures/CAPLfunctionOnAnyFctCalled.md): Is called whenever a provided method of a distributed object derived from the given interface is called.
- [on any_fct_calling](EventProcedures/CAPLfunctionOnAnyFctCalling.md): Is called whenever a method of a distributed object derived from the given interface is about to be called.
- [on any_fct_returned](EventProcedures/CAPLfunctionOnAnyFctRetured.md): Is called whenever a method of a distributed object derived from the given interface has returned at the consumer.
- [on any_fct_returning](EventProcedures/CAPLfunctionOnAnyFctReturning.md): Is called whenever a method of a distributed object derived from the given interface is about to return its answer at the provider.
- [on any_monitored_value_change](EventProcedures/CAPLfunctionOnAnyMonitoredValueChange .md): Is called whenever a value of the given set is changed at a monitoring object.
- [on any_monitored_value_update](EventProcedures/CAPLfunctionOnAnyMonitoredValueUpdate.md): Is called whenever a value of the given set is updated at a monitoring object.
- [on any_value_change](EventProcedures/CAPLfunctionOnAnyValueChange.md): Is called whenever a value of the given set changes.
- [on any_value_update](EventProcedures/CAPLfunctionOnAnyValueUpdate.md): Is called whenever a value of the given set is updated.
- [on fct_Called](EventProcedures/CAPLfunctionOnfctCalled.md): Is called when a service function is called.
- [on fct_Calling](EventProcedures/CAPLfunctionOnfctCalling.md): Is called when a service function is about to be called.
- [on fct_Returned](EventProcedures/CAPLfunctionOnfctReturned.md): Is called when a service function answer is returned to the consumer.
- [on fct_Returning](EventProcedures/CAPLfunctionOnfctReturning.md): Is called when a service function is about to return its answer.
- [on transmit_announce](EventProcedures/CAPLfunctionOnTransmitAnnounce.md): Is called whenever a provided data, event, or field member transmits an announce via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_any_announce](EventProcedures/CAPLfunctionOnTransmitAnyAnnounce.md): Is called whenever an instance of a provided data, event, or field member transmits an announce via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_any_call](EventProcedures/CAPLfunctionOnTransmitAnyCall.md): Is called whenever an instance of a consumed method member transmits a value via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_any_return](EventProcedures/CAPLfunctionOnTransmitAnyReturn.md): Is called whenever an instance of a provided method member transmits a return via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_any_subscribe](EventProcedures/CAPLfunctionOnTransmitAnySubscribe.md): Is called whenever an instance of a consumed data, event, or field member transmits a subscribe via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_any_unannounce](EventProcedures/CAPLfunctionOnTransmitAnyUnannounce.md): Is called whenever an instance of a provided data, event, or field member transmits an unannounce via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_any_unsubscribe](EventProcedures/CAPLfunctionOnTransmitAnyUnsubscribe.md): Is called whenever an instance of a consumed data, event, or field member transmits an unsubscribe via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_any_value](EventProcedures/CAPLfunctionOnTransmitAnyValue.md): Is called whenever an instance of a provided data, event, or field interface member transmits a value via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_call](EventProcedures/CAPLfunctionOnTransmitCall.md): Is called whenever a consumed method member transmits a value via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_return](EventProcedures/CAPLfunctionOnTransmitReturn.md): Is called whenever a provided method member transmits a value via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_subscribe](EventProcedures/CAPLfunctionOnTransmitSubscribe.md): Is called whenever a consumed data, event, or field member transmits a subscribe via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_unannounce](EventProcedures/CAPLfunctionOnTransmitUnannounce.md): Is called whenever a provided data, event, or field member transmits an unannounce via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_unsubscribe](EventProcedures/CAPLfunctionOnTransmitUnsubscribe.md): Is called whenever a consumed data, event, or field member transmits an unsubscribe via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on transmit_value](EventProcedures/CAPLfunctionOnTransmitValue.md): Is called whenever a provided data, event, or field member transmits a value via the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [on value_change](EventProcedures/CAPLfunctionOnValueChange.md): Is called when a distributed object value changes.
- [on value_update](EventProcedures/CAPLfunctionOnValueUpdate.md): Is called when a distributed object value is updated.

## Functions 

- [lookupDistObj](Functions/CAPLfunctionLookupDistObj.md): Obtains an object by using a string.
- [lookupDistObjContainer](Functions/CAPLfunctionLookupDistObjContainer.md): Obtains a container by using a string.
- [lookupDistObjReference](Functions/CAPLfunctionLookupDistObjReference.md): Obtains a reference by using a string.
- [lookupVirtNet](Functions/CAPLfunctionLookupVirtNet.md): Obtains a virtual network by using a string.
- [getAttribute](Functions/CAPLfunctionGetAttribute.md): Reads an attribute value from an attributable object.
- [resetDistObjValues](Functions/CAPLfunctionResetDistObjValues.md): Resets all distributed object member values to their initial values.
- [setAttribute](Functions/CAPLfunctionSetAttribute.md): Writes an attribute value at an attributable object.

## Methods 

- [Binding::AnnouncementStateReceived](Methods/CAPLfunctionBindingAnnouncementStateReceived.md): Sets the announcement state of a provided data, event, or field member value that uses the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md) and **PublishSubscribe** communication pattern with announcements.
- [Binding::CallReceived](Methods/CAPLfunctionBindingCallReceived.md): Sets the in-parameters for a call at a provided method member that uses the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [Binding::CreateCallContext](Methods/CAPLfunctionBindingCreateCallContext.md): Creates a new call context with the given method member prototype and request ID.
- [Binding::ReturnReceived](Methods/CAPLfunctionBindingReturnReceived.md): Sets the out-parameters for a returning call at a consumed method member that uses the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [Binding::SetInParameter](Methods/CAPLfunctionBindingSetInParameter.md): Sets the value of an in-parameter. It is required because the normal assignment for inout-parameters only writes to the out-value.
- [Binding::SubscriptionStateReceived](Methods/CAPLfunctionBindingSubscriptionStateReceived.md): Sets the subscription state of a consumed data, event, or field member value that uses the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md) and **PublishSubscribe** communication pattern.
- [Binding::ValueReceived](Methods/CAPLfunctionBindingValueReceived.md): Sets a value of a consumed data, event, or field member value that uses the [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [distObjBlueprint::AddVirtualNetwork](Methods/CAPLfunctiondistObjBlueprintAddVirtualNetwork.md): Adds a virtual network to the blueprint.
- [distObjBlueprint::Clear](Methods/CAPLfunctiondistObjBlueprintClear.md): Removes all attributes and virtual networks from the blueprint.
- [distObjBlueprint::CopyFromObject](Methods/CAPLfunctiondistObjBlueprintCopyFromObject.md): Recursively copies all attributes and virtual network from the given object and its members to the blueprint.
- [distObjBlueprint::CreateMonitoringObject](Methods/CAPLfunctiondistObjBlueprintCreateMonitoringObject.md): Creates a dynamic monitoring object from the blueprint.
- [distObjBlueprint::CreateObject](Methods/CAPLfunctiondistObjBlueprintCreateObject.md): Creates a dynamic object from the blueprint.
- [distObjBlueprint::GetAttribute](Methods/CAPLfunctiondistObjBlueprintGetAttribute.md): Gets the value of an attribute that is set at the blueprint.
- [distObjBlueprint::RemoveAttribute](Methods/CAPLfunctiondistObjBlueprintRemoveAttribute.md): Removes an attribute from the blueprint.
- [distObjBlueprint::RemoveVirtualNetwork](Methods/CAPLfunctiondistObjBlueprintRemoveVirtualNetwork.md): This method removes a virtual network from the blueprint.
- [distObjBlueprint::SetAttribute](Methods/CAPLfunctiondistObjBlueprintSetAttribute.md): Sets an attribute at the blueprint.
- [distObjContainerRef::Create](Methods/CAPLfunctiondistObjContainerRefCreate.md): Creates a new object at the given index.
- [distObjContainerRef::Erase](Methods/CAPLfunctiondistObjContainerRefErase.md): Replaces an object at the given index with an invalid object.
- [distObjContainerRef::PopBack](Methods/CAPLfunctiondistObjContainerRefPopBack.md): Removes an element at the end of the container.
- [distObjContainerRef::PushBack](Methods/CAPLfunctiondistObjContainerRefPushBack.md): Adds an element at the end of the container.
- [distObjContainerRef::Resize](Methods/CAPLfunctiondistObjContainerRefResize.md): Resizes the container.
- [distObjEventRef::Trigger](Methods/CAPLfunctiondistObjEventRefTrigger.md): Triggers an update event on the member value.
- [distObjInterface::CreateMonitoringObject](Methods/CAPLfunctiondistObjInterfaceCreateMonitoringObject.md): Creates a dynamic monitoring object from the blueprint.
- [distObjInterface::CreateObject](Methods/CAPLfunctiondistObjInterfaceCreateObject.md): Creates a dynamic object from the blueprint.
- [distObjInterface::CreateObjectBlueprint](Methods/CAPLfunctiondistObjInterfaceCreateObjectBlueprint.md): Creates a blueprint for the given interface.
- [distObjInterface::CreateReverseObjectBlueprint](Methods/CAPLfunctiondistObjInterfaceCreateReverseObjectBlueprint.md): Creates a blueprint for the reverse of the given interface.
- [distObjInterface::DestroyObject](Methods/CAPLfunctiondistObjInterfaceDestroyObject.md): Destroys a dynamic object.
- [distObjInterface::DestroyMonitoringObject](Methods/CAPLfunctiondistObjInterfaceDestroyMonitoringObject.md): Destroys a dynamic monitoring object from the blueprint.
- [distObjMemberBlueprint::GetAttribute](Methods/CAPLfunctiondistObjMemberBlueprintGetAttribute.md): Gets the value of an attribute that is set at the member blueprint.
- [distObjMemberBlueprint::RemoveAttribute](Methods/CAPLfunctiondistObjMemberBlueprintRemoveAttribute.md): Removes an attribute from the member blueprint.
- [distObjMemberBlueprint::RemoveVirtualNetwork](Methods/CAPLfunctiondistObjMemberBlueprintRemoveVirtualNetwork.md): Removes the virtual network from the member blueprint.
- [distObjMemberBlueprint::SetAttribute](Methods/CAPLfunctiondistObjMemberBlueprintSetAttribute.md): Sets an attribute at the member blueprint.
- [distObjMemberBlueprint::SetInitialValue](Methods/CAPLfunctiondistObjMemberBlueprintSetInitialValue.md): Sets the initial value of the member blueprint.
- [distObjMemberBlueprint::SetVirtualNetwork](Methods/CAPLfunctiondistObjMemberBlueprintSetVirtualNetwork.md): Sets the virtual network of the member blueprint.
- [distObjMemberRef::Announce](Methods/CAPLfunctiondistObjMemberRefAnnounce.md): Announces the member.
- [distObjMemberRef::IsConnected](Methods/CAPLfunctiondistObjRefIsConnected.md): Checks if the object member is connected to its assigned virtual network.
- [distObjMemberRef::Subscribe](Methods/CAPLfunctiondistObjMemberRefSubscribe.md): Subscribes the member.
- [distObjMemberRef::Unannounce](Methods/CAPLfunctiondistObjMemberRefUnannounce.md): Unannounces the member.
- [distObjMemberRef::Unsubscribe](Methods/CAPLfunctiondistObjMemberRefUnsubscribe.md): Unsubscribes the member.
- [distObjMethodRef::Call](Methods/CAPLfunctiondistObjMethodRefCall.md): Synchronous call to a method member.
- [distObjMethodRef::CallAsync](Methods/CAPLfunctiondistObjMethodRefCallAsync.md): Asynchronous call to a method member.
- [distObjMethodRef::Call_Phys](Methods/CAPLfunctiondistObjMethodRefCallPhys.md): Synchronous call to a method member.
- [distObjMethodRef::CallAsync_Phys](Methods/CAPLfunctiondistObjMethodRefCallAsyncPhys.md): Asynchronous call to a method member.
- [distObjRef::AnnounceAll](Methods/CAPLfunctiondistObjRefAnnounceAll.md): This is a collective operation that announces all provided members which use the publish-subscribe pattern with announcements.
- [distObjRef::Connect](Methods/CAPLfunctiondistObjRefConnect.md): This is a collective operation that connects every member of the object with its virtual network.
- [distObjRef::ConnectTo](Methods/CAPLfunctiondistObjRefConnectTo.md): This is a collective operation that connects every member of the object, if it is assigned to the given virtual network.
- [distObjRef::Disconnect](Methods/CAPLfunctiondistObjRefDisconnect.md): This is a collective operation that disconnects every member of the object from its virtual network.
- [distObjRef::DisconnectFrom](Methods/CAPLfunctiondistObjRefDisconnectFrom.md): This is a collective operation that disconnects every member of the object, if it is assigned to the given virtual network.
- [distObjRef::IsConnected](Methods/CAPLfunctiondistObjRefIsConnected.md): Checks if every member of the object is connected to its virtual network.
- [distObjRef::IsConnectedTo](Methods/CAPLfunctiondistObjRefIsConnectedTo.md): Checks if every member of the object is connected, if it is assigned to the given virtual network.
- [distObjRef::SubscribeAll](Methods/CAPLfunctiondistObjRefSubscribeAll.md): This is a collective operation that subscribes all consumed members which use the publish-subscribe pattern.
- [distObjRef::UnannounceAll](Methods/CAPLfunctiondistObjRefUnannounceAll.md): This is a collective operation that unannounces all provided members which use the publish-subscribe pattern with announcements.
- [distObjRef::UnsubscribeAll](Methods/CAPLfunctiondistObjRefUnsubscribeAll.md): This is a collective operation that unsubscribes all consumed members which use the publish-subscribe pattern.
- [distObjReferenceRef::ResetTarget](Methods/CAPLfunctiondistObjReferenceRefResetTarget.md): Resets the target object of the reference.
- [distObjReferenceRef::SetTarget](Methods/CAPLfunctiondistObjReferenceRefSetTarget.md): Sets the target object of the reference.
- [distObjReferenceRef::SetTargetByPath](Methods/CAPLfunctiondistObjReferenceRefSetTargetByPath.md): Sets the target object of the reference.
- [valueHandle::BeginValueBulkUpdate](Methods/CAPLfunctionValueBeginValueBulkUpdate.md): Begins a bulk update of the value.
- [valueHandle::ClearChangeFlag](Methods/CAPLfunctionValueClearChangeFlag.md): Clears the change flag of the value.
- [valueHandle::ClearUpdateFlag](Methods/CAPLfunctionValueClearUpdateFlag.md): Clears the update flag of the value.
- [valueHandle::EndValueBulkUpdate](Methods/CAPLfunctionValueEndValueBulkUpdate.md): Ends a bulk update of the value.
- [valueHandle::GetChangeCount](Methods/CAPLfunctionValueGetChangeCount.md): Returns the change count of the value.
- [valueHandle::GetUpdateCount](Methods/CAPLfunctionValueGetUpdateCount.md): Returns the update count of the value.
- [valueHandle::GetValueState](Methods/CAPLfunctionValueGetValueState.md): Returns the state of the value.
- [valueHandle::ResetValueState](Methods/CAPLfunctionValueResetValueState.md): Resets the state of the value.

## Objects 

- [attributable](Objects/CAPLfunctionAttributable.md): The type of objects that can have attributes.
- [attribute](Objects/CAPLfunctionAttribute.md): The types of attributes for distributed objects.
- [bindingError](Objects/CAPLfunctionBindingError.md): Refers to a singleton object that can be used to programmatically detect errors in the binding of distributed objects.
- [Binding](Objects/CAPLfunctionBinding.md): This type provides static methods which are used for implementing a [CAPL binding](../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).
- [bytes](Objects/CAPLfunctionBytes.md): The corresponding CAPL type for the bytes type in [vCDL](../../vCDL/Language/vCDLBytesDataTypes.md).
- [distObjBlueprint](Objects/CAPLfunctiondistObjBlueprint.md): A blueprint type for dynamically creating distributed objects.
- [distObjContainerRef](Objects/CAPLfunctiondistObjContainerRef.md): References a container of distributed objects or references.
- [distObjDataRef](Objects/CAPLfunctiondistObjDataRef.md): References a distributed object data member.
- [distObjEventRef](Objects/CAPLfunctiondistObjEventRef.md): References a distributed object event member.
- [distObjFieldRef](Objects/CAPLfunctiondistObjFieldRef.md): References a distributed object field member.
- [distObjInterface](Objects/CAPLfunctiondistObjInterface.md): A type for creating blueprints and dynamic distributed objects.
- [distObjInterfaceMember](Objects/CAPLfunctiondistObjInterfaceMember.md): The types of distributed object interface members.
- [distObjMemberBlueprint](Objects/CAPLfunctiondistObjMemberBlueprint.md): A type for configuring the attributes and virtual network of an object blueprint member.
- [distObjMemberRef](Objects/CAPLfunctiondistObjMemberRef.md): References a distributed object member.
- [distObjMethodRef](Objects/CAPLfunctiondistObjMethodRef.md): References a distributed object method member.
- [distObjRef](Objects/CAPLfunctiondistObjRef.md): References a distributed object that is derived from the denoted interface.
- [distObjReferenceRef](Objects/CAPLfunctiondistObjReferenceRef.md): References a reference to a distributed object that is derived from the given interface.
- [monitoringDistObjContainerRef](Objects/CAPLfunctionMonitoringDistObjContainerRef.md): References a container of monitoring distributed objects.
- [monitoringDistObjDataRef](Objects/CAPLfunctionMonitoringDistObjDataRef.md): References a monitoring distributed object data member.
- [monitoringDistObjEventRef](Objects/CAPLfunctionMonitoringDistObjEventRef.md): References a monitoring distributed object event member.
- [monitoringDistObjFieldRef](Objects/CAPLfunctionMonitoringDistObjFieldRef.md): References a monitoring distributed object field member.
- [monitoringDistObjMemberRef](Objects/CAPLfunctionMonitoringDistObjMemberRef.md): References a monitoring distributed object member.
- [monitoringDistObjMethodRef](Objects/CAPLfunctionMonitoringDistObjMethodRef.md): References a monitoring distributed object method member.
- [monitoringDistObjRef](Objects/CAPLfunctionMonitoringDistObjRef.md): References a monitoring distributed object that is derived from the denoted interface.
- [virtNet](Objects/CAPLfunctionvirtNet.md): References a virtual network.

[Communication Concept](../../CANoeCANalyzer/CommunicationConcept/CC.md) • [Programming with Communication Concept](../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
