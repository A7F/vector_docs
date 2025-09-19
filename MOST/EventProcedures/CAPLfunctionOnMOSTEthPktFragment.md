[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTEthPktFragment.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostEthPktFragment

# OnMostEthPktFragment

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostEthPktFragment();
```

## Description

The event procedure `OnMostEthPktFragment` is called when the spy detects an incomplete Ethernet packet transmission.

The following functions are available for evaluating the event:

- `long mostEventChannel()`

  Returns the channel of the packet event.

- `long mostEventTime()`

  Returns the time stamp of the event (Units: 10 µs).

- `float mostEventTimeNs()`

  Returns the time stamp of the event (Units: 1 ns).

- `long mostEventOrigTime()`

  Returns the hardware generated time stamp of the event (Units: 10 µs).

- `long mostEthPktFragmentDlc()`

  Number of transported data bytes.

- `long mostEthPktFragmentGetData(byte[] buffer, long cnt)`

  Tries to copy cnt data bytes to a provided buffer. Returns the actual number of copied bytes.

**Note**: Due to performance reasons only the first transmitted data bytes are stored in the fragment event.

All following functions return -1 if the corresponding data field is invalid (i.e. event was too short to contain the information).

- `int64 mostEthPktSrcMacAdr(), int64 mostEthPktDestMacAdr()`

  Returns the 48 bit source or destination Ethernet address.

- `long mostEthPktFragmentAck()`

  Returns the acknowledge code.

- `long mostEthPktFragmentPAck()`

  Returns the preemptive acknowledge from the potential packet receiver(s) to the packet transmitter.

- `dword mostEthPktFragmentCRC()`

  Returns the CRC value.

- `long mostEthPktFragmentCAck()`

  Returns the CRC acknowledge code.

- `long mostEthPktFragmentAnnouncedDlc()`

  Returns the announced data length at start of transmission. In general, the announced length is not equal to the actual number of transmitted data bytes for fragments.

In nodal sequences (Measurement Setup) a fragment can be passed to the next node by the outputMostEthPktFragmentThis command.

## Parameters

—

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
