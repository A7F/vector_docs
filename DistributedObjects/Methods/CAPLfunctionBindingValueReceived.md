[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctionBindingValueReceived.md)

# Binding::ValueReceived

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » Binding::ValueReceived

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

- `long Binding::ValueReceived(distObjDataRef * member, double value);`
- `long Binding::ValueReceived(distObjDataRef * member, long value);`
- `long Binding::ValueReceived(distObjDataRef * member, dword value);`
- `long Binding::ValueReceived(distObjDataRef * member, int64 value);`
- `long Binding::ValueReceived(distObjDataRef * member, qword value);`
- `long Binding::ValueReceived(distObjDataRef * member, char value[]);`
- `long Binding::ValueReceived(distObjDataRef * member, dataTypeHandle value);`
- `long Binding::ValueReceived(distObjEventRef * member, double value);`
- `long Binding::ValueReceived(distObjEventRef * member, long value);`
- `long Binding::ValueReceived(distObjEventRef * member, dword value);`
- `long Binding::ValueReceived(distObjEventRef * member, int64 value);`
- `long Binding::ValueReceived(distObjEventRef * member, qword value);`
- `long Binding::ValueReceived(distObjEventRef * member, char value[]);`
- `long Binding::ValueReceived(distObjEventRef * member, dataTypeHandle value);`
- `long Binding::ValueReceived(distObjFieldRef * member, double value);`
- `long Binding::ValueReceived(distObjFieldRef * member, long value);`
- `long Binding::ValueReceived(distObjFieldRef * member, dword value);`
- `long Binding::ValueReceived(distObjFieldRef * member, int64 value);`
- `long Binding::ValueReceived(distObjFieldRef * member, qword value);`
- `long Binding::ValueReceived(distObjFieldRef * member, char value[]);`
- `long Binding::ValueReceived(distObjFieldRef * member, dataTypeHandle value);`

## Description

Sets a value of a consumed data, event, or field member value that uses the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).

The called overload must correspond to the member value type. Otherwise, an error code is returned.

## Parameters

- **member**: Member which receives a value via the CAPL binding.
- **value**: Value to be received.

## Return Values

- **0**: OK
- **1**: No CAPL binding configured
- **5**: Wrong datatype

## Example

```plaintext
// Transmit an event via CAN messages.

// example.vcdl
version 1.3;
namespace SomeNamespace {
  interface Example {
    [Binding="CAPL", CommunicationPattern=SendReceive]
    consumed event int32 SomeEvent;
  }
  object Consumer : Example {}
  object Provider : reverse<Example> {}
}

// provider.can
on key 'a' {
  $Provider.SomeEvent++;
}

// provider_binding.can
on transmit_value Provider.SomeEvent {
  message SomeEvent_Value msg;
  msg.value = $this;
  output(msg);
}

// consumer.can
on value_update Consumer.SomeEvent {
  write("received %d", $this);
}

// consumer_binding.can
on message SomeEvent_Value {
  Binding::ValueReceived(Consumer.SomeEvent, (long)this.value);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)