[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionAbstractUnsubscribeField.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » Abstract_UnsubscribeField

# Abstract_UnsubscribeField (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long Abstract_UnsubscribeField(consumedFieldRef * field);
```

## Description

Unsubscribes for a service field if abstract binding is used. Note that this is more **low-level**; usually it's more convenient to call [consumedFieldRef::AbstractReleaseField](../Methods/CAPLfunctionConsumedFieldRefAbstractReleaseField.md) on the field.

## Parameters

- **field**: Field which shall be unsubscribed.

## Return Values

- **0**: Success
- **1**: Endpoint is not simulated
- **2**: Communication object does not use abstract binding
- **3**: Field does not have a notification
- **< 0**: Other error, e.g. field variable is not initialized

## Example

```plaintext
Abstract_UnsubscribeField(MirrorAdjustment.consumerSide[0,0].CurrentPosition);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [Abstract_SubscribeField](CAPLfunctionAbstractSubscribeField.md) • [SOMEIP_UnsubscribeEventGroup](CAPLfunctionSOMEIPUnsubscribeEventGroup.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)