[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/EventProcedures/CAPLfunctionOnValueChange.md)

## CAPL Functions » Communication Objects » on value_change

# on value_change (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

```plaintext
on value_change <value>;
```

### Description

The event procedure is called whenever the specified value changes. It’s not called when the value is updated, but does not change. You can use the event procedure for all values of communication objects, including e.g. signal and event values, **LatestCall** or **LatestReturn** of methods, service states, etc.

### Parameters

- **`<value>`**: Designates the value on which the procedure shall be called.

### Selectors

- **ChangeTimeNS**: Last time the value was changed, in nanoseconds since measurement start.  
  Type: `int64`  
  Access Limitation: Read only

- **UpdateTimeNS**: Last time the value was updated, in nanoseconds since measurement start.  
  Type: `int64`  
  Access Limitation: Read only

### Example

```plaintext
on value_change MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition
{
  write("New position received: (%d,%d)", $this.x.phys, $this.y.phys);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on value_update](CAPLfunctionOnValueUpdate.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)