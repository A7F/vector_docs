[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionGetConsumedServiceRef.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » GetConsumedServiceRef

# GetConsumedServiceRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `consumedServiceRef * [consumedEventRef](../Objects/CAPLfunctionConsumedEventRef.md)::GetConsumedService();`
- `consumedServiceRef * [consumedFieldRef](../Objects/CAPLfunctionConsumedFieldRef.md)::GetConsumedService();`
- `consumedServiceRef * [consumedPDURef](../Objects/CAPLfunctionConsumedPDURef.md)::GetConsumedService();`
- `consumedServiceRef * [consumedMethodRef](../Objects/CAPLfunctionConsumedMethodRef.md)::GetConsumedService();`

## Description

Returns a reference to the enclosing service for the referred object.

## Parameters

—

## Return Values

A reference to the enclosing service. An invalid reference if the object is invalid.

## Example

—

- Technical References are only available in English

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)