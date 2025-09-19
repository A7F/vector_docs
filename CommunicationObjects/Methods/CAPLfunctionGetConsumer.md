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
