[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionAbstractGetDisplayName.md)

**CAPL Functions** » **Communication Objects** » **Abstract_GetDisplayName**

# Abstract_GetDisplayName (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long Abstract_GetDisplayName(addressHandle address, char[] buffer);
```

## Description

Retrieves a display name for an endpoint with an abstract binding pseudo address. The name may have been set with [Abstract_CreateAddress](CAPLfunctionAbstractCreateAddress.md).

## Parameters

- **address**: Address of the endpoint.
- **buffer**: Receives the display name.

## Return Values

- **0**: success
- **-1**: buffer is too small
- **-2**: address not found

## Example

```c
ret = Abstract_GetDisplayName(newProvider.Address, buffer);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [SD_SetAddress](CAPLfunctionSDSetAddress.md) • [Abstract_CreateAddress](CAPLfunctionAbstractCreateAddress.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)