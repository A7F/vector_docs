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
