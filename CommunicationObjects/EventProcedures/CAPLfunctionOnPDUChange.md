[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/EventProcedures/CAPLfunctionOnPDUChange.md)

**CAPL Functions** » **Communication Objects** » **on PDU_change**

# on PDU_change (obsolete)

**Valid for**: CANoe DE

## Function Syntax

```
on PDU_change <PDU>;
```

## Description

The event procedure is called whenever the specified PDU is changed, but not if it is simply updated without a value change. You can use the event procedure only for PDUs of the new [communication concept](../../../CANoeCANalyzer/CommunicationConcept/CC.md) of CANoe.

## Parameters

- **`<PDU>`**: Designates the PDU on which the procedure shall be called.

## Selectors

- **ChangeTimeNS**: Last time the value was changed, in nanoseconds since measurement start.  
  **Type**: int64  
  **Access Limitation**: Read only

- **UpdateTimeNS**: Last time the value was updated, in nanoseconds since measurement start.  
  **Type**: int64  
  **Access Limitation**: Read only

- **<SignalName>**: Value of the signal. Must be accessed with `$this`.  
  **Type**: <data type of the signal>  
  **Access Limitation**: Read only

## Example

```plaintext
on PDU_Change Mirrors::MirrorAdjustment.consumerSide[CANoe,LeftMirror].StatusPdu
{
  write("Status %d at time %I64d", $this.health, this.ChangeTimeNS);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on PDU_update](CAPLfunctionOnPDUUpdate.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)