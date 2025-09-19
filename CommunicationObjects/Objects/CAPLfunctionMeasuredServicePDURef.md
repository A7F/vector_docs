# measuredServicePDURef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

- `measuredServicePDURef * <var>; // form 1`
- `measuredServicePDURef <PDU> <var>; // form 2`
- `measuredServicePDURef <Datatype> <var>; // form 3`

### Method Syntax

- —

### Description

References a service PDU measurement point, which means measuring a specific connection between consumer and provider for a service PDU. Not used for PDUs outside services, the data type of these is [measuredPDURef](CAPLfunctionMeasuredPDURef.md).

### Parameters

- **PDU**: PDU, determining the data type of the object.
- **Datatype**: Data type of the object (a PDU definition).

### Selectors

- **Name**: Name of the measurement endpoint  
  Type: `char[]`  
  Access Limitation: Read only

- **Path**: Full path of the measurement endpoint (including namespaces)  
  Type: `char[]`  
  Access Limitation: Read only

- **ConsumerIndex**: Index of the consumer. Note that the index may change if consumers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **ProviderIndex**: Index of the provider. Note that the index may change if providers are added or removed.  
  Type: `dword`  
  Access Limitation: Read only

- **measuredService**: The measurement point at the service.  
  Type: `measuredServiceRef *`  
  Access Limitation: Read only

- **SubscriptionState**: State of the PDU subscription:
  - Unknown: the PDUsubscription was not observed yet
  - Unsubscribed: the PDU is not subscribed
  - Subscribed: the PDU is subscribed  
  Type: `enum`  
  Access Limitation: Read only

### Example

```c
measuredServicePDURef MirrorAdjustment.StatusPDU pdu1;
pdu1 = MirrorAdjustment.measure[CANoe,LeftMirror].StatusPDU;
write("Latest x: %d", $pdu1.Position.x);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [measuredPDURef](CAPLfunctionMeasuredPDURef.md)
