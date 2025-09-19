[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionSetConsumer.md)

## SetConsumer (obsolete)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SetConsumer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Method Syntax

- `long consumedServiceRef::SetConsumer(char[] consumerPath); // form 1`
- `long consumedEventRef::SetConsumer(char[] consumerPath);`
- `long consumedFieldRef::SetConsumer(char[] consumerPath);`
- `long consumedPDURef::SetConsumer(char[] consumerPath);`
- `long consumedMethodRef::SetConsumer(char[] consumerPath);`
- `long providedServiceRef::SetConsumer(char[] consumerPath);`
- `long providedEventRef::SetConsumer(char[] consumerPath);`
- `long providedFieldRef::SetConsumer(char[] consumerPath);`
- `long providedPDURef::SetConsumer(char[] consumerPath);`
- `long providedMethodRef::SetConsumer(char[] consumerPath);`
- `long serviceConsumerRef::SetConsumer(char[] consumerPath);`
- `long eventConsumerRef::SetConsumer(char[] consumerPath);`
- `long fieldConsumerRef::SetConsumer(char[] consumerPath);`
- `long pduConsumerRef::SetConsumer(char[] consumerPath);`

---

- `long consumedServiceRef::SetConsumer(dword index); // form 2`
- `long consumedEventRef::SetConsumer(dword index);`
- `long consumedFieldRef::SetConsumer(dword index);`
- `long consumedPDURef::SetConsumer(dword index);`
- `long consumedMethodRef::SetConsumer(dword index);`
- `long providedServiceRef::SetConsumer(dword index);`
- `long providedEventRef::SetConsumer(dword index);`
- `long providedFieldRef::SetConsumer(dword index);`
- `long providedPDURef::SetConsumer(dword index);`
- `long providedMethodRef::SetConsumer(dword index);`
- `long serviceConsumerRef::SetConsumer(dword index);`
- `long eventConsumerRef::SetConsumer(dword index);`
- `long fieldConsumerRef::SetConsumer(dword index);`
- `long pduConsumerRef::SetConsumer(dword index);`

---

- `long consumedServiceRef::SetConsumer(COParticipant participant); // form 3`
- `long consumedEventRef::SetConsumer(COParticipant participant);`
- `long consumedFieldRef::SetConsumer(COParticipant participant);`
- `long consumedPDURef::SetConsumer(COParticipant participant);`
- `long consumedMethodRef::SetConsumer(COParticipant participant);`
- `long providedServiceRef::SetConsumer(COParticipant participant);`
- `long providedEventRef::SetConsumer(COParticipant participant);`
- `long providedFieldRef::SetConsumer(COParticipant participant);`
- `long providedPDURef::SetConsumer(COParticipant participant);`
- `long providedMethodRef::SetConsumer(COParticipant participant);`
- `long serviceConsumerRef::SetConsumer(COParticipant participant);`
- `long eventConsumerRef::SetConsumer(COParticipant participant);`
- `long fieldConsumerRef::SetConsumer(COParticipant participant);`
- `long pduConsumerRef::SetConsumer(COParticipant participant);`

---

- `long consumedServiceRef::SetConsumer(serviceConsumerRef * consumer); // form 4`
- `long consumedEventRef::SetConsumer(eventConsumerRef * consumer);`
- `long consumedFieldRef::SetConsumer(fieldConsumerRef * consumer);`
- `long consumedPDURef::SetConsumer(pduConsumerRef * consumer);`
- `long providedServiceRef::SetConsumer(serviceConsumerRef * consumer);`
- `long providedEventRef::SetConsumer(eventConsumerRef * consumer);`
- `long providedFieldRef::SetConsumer(fieldConsumerRef * consumer);`
- `long providedPDURef::SetConsumer(pduConsumerRef * consumer);`

### Description

Sets the consumer endpoint for the CO reference.

### Parameters

- **consumerPath (form 1)**: Full path to a consumer endpoint of the referenced object, including all namespaces.
- **index (form 2)**: 0-based index of a consumer endpoint of the referenced object.
- **participant (form 3)**: A participant which contains a consumer endpoint of the referenced object.
- **consumer (form 4)**: A reference to a consumer endpoint of the referenced object.

### Return Values

- **0**: success
- **4**: Given endpoint is not of the referenced object (form 1 or form 4)
- **5**: Given participant contains no fitting endpoint of the referenced object (form 3)
- **7**: Index is invalid (form 2)
- **-1**: Object is invalid

### Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
