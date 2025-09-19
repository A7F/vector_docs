[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionOnReplaySourceStatusChanged.md)

**CAPL Functions** » **General** » **Event Procedures** » **on replaySourceStatusChanged**

# on replaySourceStatusChanged

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

`on replaySourceStatusChanged`

## Description

The event is triggered whenever the state of a replay block changes. This is when replay starts, at the first event of the replayed file, and after the last event of the replayed file.

Within the event, the following information can be used via the `this` operator:

- **this.timestamp**: The timestamp of the event, in ns.
- **this.block**: The name of the replay block that triggered the event.
- **this.status**: The new state of the block. The following values are possible:
  - **kStartOfSource = 1**: replay has started, i.e., the replay block is now running.
  - **kStartOfData = 2**: the first event of the replay file has been reached.
  - **kEndofData = 3**: the last event of the replay file has been reached.
- **this.filename**: The full path of the replayed file.

## Example

```plaintext
on replaySourceStatusChanged
{
  write("%I64d: %s: new state %d (file %s)", this.timestamp, this.block, this.status, this.source);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
