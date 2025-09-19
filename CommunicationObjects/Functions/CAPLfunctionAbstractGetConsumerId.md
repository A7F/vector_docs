# Abstract_GetConsumerId (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long Abstract_GetConsumerId(addressHandle address);
```

## Description

Returns an ID for a consumer with an abstract binding pseudo address. Through the ID, you can identify the consumer.

## Parameters

- **Address**: Address of the consumer.

## Return Values

A unique ID for the consumer.

## Example

```plaintext
id = Abstract_GetConsumerId(newConsumer.Address);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_SetAddress](CAPLfunctionSDSetAddress.md) • [Abstract_CreateAddress](CAPLfunctionAbstractCreateAddress.md) • [Abstract_GetDisplayName](CAPLfunctionAbstractGetDisplayName.md)
