[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionSetEvent.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » SetEvent

# SetEvent (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `long consumedEventRef::SetEvent(Event event);`
- `long providedEventRef::SetEvent(Event event);`
- `long eventConsumerRef::SetEvent(Event event);`
- `long eventProviderRef::SetEvent(Event event);`

## Description

Sets the referred-to event for the CO reference.

## Parameters

- **Event**: The new event.

## Return Values

- **0**: Success
- **3**: Given event doesn’t have the correct type
- **-1**: Given reference is invalid

## Example

```plaintext
consumedEventRef long cer;
cer.SetEvent(Services::Mirrors.Position);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)