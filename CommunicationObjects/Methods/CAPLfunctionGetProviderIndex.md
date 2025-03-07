[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionGetProviderIndex.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » GetProviderIndex

# GetProviderIndex (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `long consumedServiceRef::GetProviderIndex();`
- `long consumedEventRef::GetProviderIndex();`
- `long consumedFieldRef::GetProviderIndex ();`
- `long consumedPDURef::GetProviderIndex ();`
- `long consumedMethodRef::GetProviderIndex ();`
- `long providedServiceRef::GetProviderIndex ();`
- `long providedEventRef::GetProviderIndex ();`
- `long providedFieldRef::GetProviderIndex ();`
- `long providedPDURef::GetProviderIndex ();`
- `long providedMethodRef::GetProviderIndex ();`
- `long providedServiceRef::GetProviderIndex ();`
- `long serviceProviderRef::GetProviderIndex ();`
- `long eventProviderRef::GetProviderIndex ();`
- `long fieldProviderRef::GetProviderIndex ();`
- `long pduProviderRef::GetProviderIndex ();`

## Description

Returns the provider index selected for the CO reference.

## Return Values

If the object is valid and refers to a valid endpoint, returns the index of that endpoint. Else returns -1.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)