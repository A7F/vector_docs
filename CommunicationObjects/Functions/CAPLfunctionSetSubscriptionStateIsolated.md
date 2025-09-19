# SetSubscriptionStateIsolated (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `void SetSubscriptionStateIsolated(providedEventRef * event, dword subscribed); // form 1`
- `void SetSubscriptionStateIsolated(consumedEventRef * event, dword subscribed); // form 2`
- `void SetSubscriptionStateIsolated(providedFieldRef * field, dword subscribed); // form 3`
- `void SetSubscriptionStateIsolated(consumedFieldRef * field, dword subscribed); // form 4`
- `void SetSubscriptionStateIsolated(providedPDURef * pdu, dword subscribed); // form 5`
- `void SetSubscriptionStateIsolated(consumedPDURef * pdu, dword subscribed); // form 6`

## Description

Sets the subscription state for an object, for a specific consumer – provider combination, independent of network communication. Normally, the subscription state will be set by the CANoe simulation depending on the observed communication. You can override the behavior if you for example want to test reaction to specific faulty behavior.

## Parameters

- **event**: Event and endpoints for which the state shall be set.
- **field**: Field and endpoints for which the state shall be set.
- **pdu**: PDU and endpoints for which the state shall be set.
- **subscribed**: 1 to set the state to subscribed, 0 to set it to unsubscribed.

## Return Values

—

## Example

```c
SetSubscriptionStateIsolated(field1, 0);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
