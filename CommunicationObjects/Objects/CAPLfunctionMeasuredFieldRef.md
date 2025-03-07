[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Objects/CAPLfunctionMeasuredFieldRef.md)

CAPL Functions » [Communication Objects](../CAPLfunctionsCOOverview.md) » measuredFieldRef

# measuredFieldRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `measuredFieldRef * <var>; // form 1`
- `measuredFieldRef <Field> <var>; // form 2`
- `measuredFieldRef <Datatype> <var>; // form 3`

## Method Syntax

—

## Description

References a field measurement point, which means measuring a specific connection between consumer and provider for a service field.

## Parameters

- **Field**: Field, determining the data type of the object.
- **Datatype**: Data type of the object.

## Selectors

- **Name**
  - Type: `char[]`
  - Access Limitation: Read only

- **Path**
  - Type: `char[]`
  - Access Limitation: Read only

- **ConsumerIndex**
  - Type: `dword`
  - Access Limitation: Read only

- **ProviderIndex**
  - Type: `dword`
  - Access Limitation: Read only

- **measuredService**
  - Type: `measuredServiceRef *`
  - Access Limitation: Read only

- **SubscriptionState**
  - Type: `enum`
  - Access Limitation: Read only
  - State of the field subscription:
    - Unknown: the field subscription was not observed yet
    - Unsubscribed: the field is not subscribed
    - Subscribed: the field is subscribed

## Example

```plaintext
measuredFieldRef MirrorAdjustment.Position field;
field = MirrorAdjustment.measure[CANoe,LeftMirror].Position;
write("Latest x: %d", $field.x);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)