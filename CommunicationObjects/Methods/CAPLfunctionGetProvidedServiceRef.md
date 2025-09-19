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
