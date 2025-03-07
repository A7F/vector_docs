[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionClear.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » Clear

# Clear (obsolete)

**Valid for**: CANoe DE

## Method Syntax

- `void consumedEventRef::Clear();`
- `void consumedFieldRef::Clear();`
- `void consumedMethodRef::Clear();`
- `void consumedPDURef::Clear();`
- `void consumedServiceRef::Clear();`
- `void eventConsumerRef::Clear();`
- `void eventProviderRef::Clear();`
- `void fieldConsumerRef::Clear();`
- `void fieldProviderRef::Clear();`
- `void pduConsumerRef::Clear();`
- `void pduProviderRef::Clear();`
- `void providedEventRef::Clear();`
- `void providedFieldRef::Clear();`
- `void providedMethodRef::Clear();`
- `void providedPDURef::Clear();`
- `void providedServiceRef::Clear();`
- `void rxPDURef::Clear();`
- `void rxSignalRef::Clear();`
- `void serviceConsumerRef::Clear();`
- `void serviceProviderRef::Clear();`
- `void txPDURef::Clear();`
- `void txSignalRef::Clear();`

## Description

Clears the CO reference. Afterward, the reference is invalid and can only be used by setting another target object, e.g. through SetService or SetPDU.

## Parameters

—

## Return Values

—

## Example

—

• Technical References are only available in English

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)