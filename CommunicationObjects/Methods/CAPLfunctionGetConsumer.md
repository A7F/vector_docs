[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionGetConsumer.md)

## CAPL Functions » Communication Objects » GetConsumer

# GetConsumer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `COParticipant consumedServiceRef::GetConsumer();`
- `COParticipant consumedEventRef::GetConsumer();`
- `COParticipant consumedFieldRef::GetConsumer();`
- `COParticipant consumedMethodRef::GetConsumer();`
- `COParticipant consumedPDURef::GetConsumer();`
- `COParticipant providedServiceRef::GetConsumer();`
- `COParticipant providedEventRef::GetConsumer();`
- `COParticipant providedFieldRef::GetConsumer();`
- `COParticipant providedPDURef::GetConsumer();`
- `COParticipant providedMethodRef::GetConsumer();`
- `COParticipant serviceConsumerRef::GetConsumer();`
- `COParticipant eventConsumerRef::GetConsumer();`
- `COParticipant fieldConsumerRef::GetConsumer();`
- `COParticipant pduConsumerRef::GetConsumer();`

## Description

Returns the consumer participant selected for the CO reference.

## Parameters

—

## Return Values

If the object is valid and refers to an endpoint which is assigned to a participant, returns a reference to that participant. Else returns an invalid reference.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)