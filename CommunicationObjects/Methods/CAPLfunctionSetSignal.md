# SetSignal (obsolete)

[Feature availabilty for your product](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

```plaintext
long txSignalRef::SetSignal(Signal signal);
long rxSignalRef::SetSignal(Signal signal);
```

## Description

Sets the referred signal object for the CO reference.

## Parameters

- **signal**: The new signal. Note that this must be a communication object from a [data source](../../../CANoeCANalyzer/Windows/CommunicationSetup/ComSetupDataSources.md) of the new [communication concept](../../../CANoeCANalyzer/CommunicationConcept/CC.md).

## Return Values

- **0**: Success
- **3**: Given signal doesn’t have the correct type
- **-1**: Given reference is invalid

## Example

—
