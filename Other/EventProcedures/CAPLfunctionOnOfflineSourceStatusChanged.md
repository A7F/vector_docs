[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionOnOfflineSourceStatusChanged.md)

**CAPL Functions** » **General** » **Event Procedures** » on offlineSourceStatusChanged

# on offlineSourceStatusChanged

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`on offlineSourceStatusChanged`

## Description

The event is triggered whenever the state of an offline source changes. This happens when offline measurement starts, at the first event of the offline source, and after the last event of the offline source.

Within the event, the following information can be used via the `this` operator:

- **this.timestamp**: The timestamp of the event, in ns.
- **this.status**: The new state of the offline source. The following values are possible:
  - **kStartOfSource = 1**: replay has started, i.e., the offline source is now being read.
  - **kStartOfData = 2**: the first event of the offline source has been reached.
  - **kEndofData = 3**: the last event of the offline source has been reached.
- **this.filename**: The full path of the offline source.

## Example

```plaintext
on offlineSourceStatusChanged
{
  write("%I64d: new state %d (file %s)", this.timestamp, this.status, this.source);
}
```
