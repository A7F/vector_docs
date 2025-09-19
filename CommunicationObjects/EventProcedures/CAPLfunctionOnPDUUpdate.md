# on PDU_update (obsolete)

**Valid for**: CANoe DE

### Function Syntax

```
on PDU_update <PDU>;
```

### Description

The event procedure is called whenever the specified PDU is updated, regardless of whether its value has changed. You can use the event procedure only for PDUs of the new [communication concept](../../../CANoeCANalyzer/CommunicationConcept/CC.md) of CANoe.

### Parameters

- **`<PDU>`**: Designates the PDU on which the procedure shall be called.

### Selectors

- **ChangeTimeNS**: Last time the value was changed, in nanoseconds since measurement start.  
  Type: `int64`  
  Access Limitation: Read only

- **UpdateTimeNS**: Last time the value was updated, in nanoseconds since measurement start.  
  Type: `int64`  
  Access Limitation: Read only

- **`<SignalName>`**: Value of the signal. Must be accessed with `$this`.  
  Type: `<data type of the signal>`  
  Access Limitation: Read only

### Example

```plaintext
on PDU_Update Mirrors::MirrorAdjustment.consumerSide[CANoe,LeftMirror].StatusPdu
{
  write("Status %d at time %I64d", $this.health, this.ChangeTimeNS);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on PDU_change](CAPLfunctionOnPDUChange.md)
