[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionGetProvidedServiceRef.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » GetProvidedServiceRef

# GetProvidedServiceRef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `providedServiceRef * [providedEventRef](../Objects/CAPLfunctionProvidedEventRef.md)::GetProvidedService();`
- `providedServiceRef * [providedFieldRef](../Objects/CAPLfunctionProvidedFieldRef.md)::GetProvidedService();`
- `providedServiceRef * [providedPDURef](../Objects/CAPLfunctionProvidedPDURef.md)::GetProvidedService();`
- `providedServiceRef * [providedMethodRef](../Objects/CAPLfunctionProvidedMethodRef.md)::GetProvidedService();`

## Description

Returns a reference to the enclosing service for the referred object.

## Parameters

—

## Return Values

A reference to the enclosing service. An invalid reference if the object is invalid.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)