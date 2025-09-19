[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionGetProvider.md)

## GetProvider (obsolete)

**CAPL Functions** » **Communication Objects** » GetProvider

**Valid for**: CANoe DE

### Method Syntax

- `COParticipant consumedServiceRef::GetProvider();`
- `COParticipant consumedEventRef::GetProvider();`
- `COParticipant consumedFieldRef::GetProvider();`
- `COParticipant consumedPDURef::GetProvider();`
- `COParticipant consumedMethodRef::GetProvider();`
- `COParticipant providedServiceRef::GetProvider();`
- `COParticipant providedEventRef::GetProvider();`
- `COParticipant providedFieldRef::GetProvider();`
- `COParticipant providedPDURef::GetProvider();`
- `COParticipant providedMethodRef::GetProvider();`
- `COParticipant serviceProviderRef::GetProvider();`
- `COParticipant eventProviderRef::GetProvider();`
- `COParticipant fieldProviderRef::GetProvider();`
- `COParticipant pduProviderRef::GetProvider();`

### Description

Returns the provider participant selected for the CO reference.

### Parameters

—

### Return Values

If the object is valid and refers to an endpoint which is assigned to a participant, returns a reference to that participant. Else returns an invalid reference.

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
