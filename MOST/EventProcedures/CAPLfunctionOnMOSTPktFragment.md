[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTPktFragment.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostPktFragment

# OnMostPktFragment

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostPktFragment();
```

## Description

The event procedure `OnMostPktFragment` is called when the spy detects an incomplete transmission on the Packet Data channel.

The following functions are available for evaluating the event:

- `long mostEventChannel()`

  Returns the channel of the packet event.

- `long mostEventTime()`

  Returns the time stamp of the event (Units: 10 µs).

- `float mostEventTimeNs()`

  Returns the time stamp of the event (Units: 1 ns).

- `long mostEventOrigTime()`

  Returns the hardware generated time stamp of the event (Units: 10 µs).

- `long mostPktFragmentDlc()`

  Number of transported data bytes.

- `long mostPktFragmentGetData(byte[] buffer, long cnt)`

  Tries to copy cnt data bytes to a provided buffer. Returns the actual number of copied bytes.

**Note**: Due to performance reasons only the first transmitted data bytes are stored in the fragment event.

All following functions return -1 if the corresponding data field is invalid (i.e. event was too short to contain the information).

- `long mostPktFragmentSrcAdr(), long mostPktFragmentDestAdr()`

  Returns the source or destination address.

- `long mostPktFragmentAck()`

  Returns the acknowledge code.

- `long mostPktFragmentPAck()`

  Returns the preemptive acknowledge from the potential packet receiver(s) to the packet transmitter.

- `long mostPktFragmentPIndex()`

  Returns the packet index. The packet index increments by one per message from a node.

- `dword mostPktFragmentCRC()`

  Returns the CRC value.

- `long mostPktFragmentCAck()`

  Returns the CRC acknowledge code.

- `long mostPktFragmentAnnouncedDlc()`

  Returns the announced data length at start of transmission. In general, the announced length is not equal to the actual number of transmitted data bytes for fragments.

In nodal sequences (Measurement Setup) a fragment can be passed to the next node by the outputMostPktFragmentThis command.

## Parameters

—

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
