[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionGetConsumerIndex.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » GetConsumerIndex

# GetConsumerIndex (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

- `long consumedServiceRef::GetConsumerIndex();`
- `long consumedEventRef::GetConsumerIndex();`
- `long consumedFieldRef::GetConsumerIndex();`
- `long consumedMethodRef::GetConsumerIndex();`
- `long consumedPDURef::GetConsumerIndex();`
- `long providedServiceRef::GetConsumerIndex();`
- `long providedEventRef::GetConsumerIndex();`
- `long providedFieldRef::GetConsumerIndex();`
- `long providedPDURef::GetConsumerIndex();`
- `long providedMethodRef::GetConsumerIndex();`
- `long serviceConsumerRef::GetConsumerIndex();`
- `long eventConsumerRef::GetConsumerIndex();`
- `long fieldConsumerRef::GetConsumerIndex();`
- `long pduConsumerRef::GetConsumerIndex();`

## Description

Returns the consumer index selected for the CO reference.

## Return Values

If the object is valid and refers to a valid endpoint, returns the index of that endpoint. Else returns -1.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)