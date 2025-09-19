[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionSetProvider.md)

## SetProvider (obsolete)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SetProvider

**Valid for**: CANoe DE

### Method Syntax

- `long providedServiceRef::SetProvider(char[] providerPath); // form 1`
- `long providedEventRef::SetProvider(char[] providerPath);`
- `long providedFieldRef::SetProvider(char[] providerPath);`
- `long providedPDURef::SetProvider(char[] providerPath);`
- `long providedMethodRef::SetProvider(char[] providerPath);`
- `long consumedServiceRef::SetProvider(char[] providerPath);`
- `long consumedEventRef::SetProvider(char[] providerPath);`
- `long consumedFieldRef::SetProvider(char[] providerPath);`
- `long consumedPDURef::SetProvider(char[] providerPath);`
- `long consumedMethodRef::SetProvider(char[] providerPath);`
- `long serviceProviderRef::SetProvider(char[] providerPath);`
- `long eventProviderRef::SetProvider(char[] providerPath);`
- `long fieldProviderRef::SetProvider(char[] providerPath);`
- `long pduProviderRef::SetProvider(char[] providerPath);`

---

- `long providedServiceRef::SetProvider(dword index); // form 2`
- `long providedEventRef::SetProvider(dword index);`
- `long providedFieldRef::SetProvider(dword index);`
- `long providedPDURef::SetProvider(dword index);`
- `long providedMethodRef::SetProvider(dword index);`
- `long consumedServiceRef::SetProvider(dword index);`
- `long consumedEventRef::SetProvider(dword index);`
- `long consumedFieldRef::SetProvider(dword index);`
- `long consumedPDURef::SetProvider(dword index);`
- `long consumedMethodRef::SetProvider(dword index);`
- `long serviceProviderRef::SetProvider(dword index);`
- `long eventProviderRef::SetProvider(dword index);`
- `long fieldProviderRef::SetProvider(dword index);`
- `long pduProviderRef::SetProvider(dword index);`

---

- `long providedServiceRef::SetProvider(COParticipant participant); // form 3`
- `long providedEventRef::SetProvider(COParticipant participant);`
- `long providedFieldRef::SetProvider(COParticipant participant);`
- `long providedPDURef::etProvider(COParticipant participant);`
- `long providedMethodRef::SetProvider(COParticipant participant);`
- `long consumedServiceRef::SetProvider(COParticipant participant);`
- `long consumedEventRef::SetProvider(COParticipant participant);`
- `long consumedFieldRef::SetProvider(COParticipant participant);`
- `long consumedPDURef::SetProvider(COParticipant participant);`
- `long consumedMethodRef::SetProvider(COParticipant participant);`
- `long serviceProviderRef::SetProvider(COParticipant participant);`
- `long eventProviderRef::SetProvider(COParticipant participant);`
- `long fieldProviderRef::SetProvider(COParticipant participant);`
- `long pduProviderRef::SetProvider(COParticipant participant);`

---

- `long providedServiceRef::SetProvider(serviceProviderRef * provider); // form 4`
- `long providedEventRef::SetProvider(eventProviderRef * provider);`
- `long providedFieldRef::SetProvider(fieldProviderRef * provider);`
- `long providedPDURef::SetProvider(pduProviderRef * provider);`
- `long consumedServiceRef::SetProvider(serviceProviderRef * provider);`
- `long consumedEventRef::SetProvider(eventProviderRef * provider);`
- `long consumedFieldRef::SetProvider(fieldProviderRef * provider);`
- `long consumedPDURef::SetProvider(pduProviderRef * provider);`

### Description

Sets the provider endpoint for the CO reference.

### Parameters

- **providerPath (form 1)**: Full path to a provider endpoint of the referenced object, including all namespaces.
- **index (form 2)**: 0-based index of a provider endpoint of the referenced object.
- **participant (form 3)**: A participant which contains a provider endpoint of the referenced object.
- **provider (form 4)**: A reference to a provider endpoint of the referenced object.

### Return Values

- **0**: Success
- **4**: Given endpoint is not of the referenced object (form 1 or form 4)
- **5**: Given participant contains no fitting endpoint of the referenced object (form 3)
- **7**: Index is invalid (form 2)
- **-1**: Object is invalid

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
