[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/CAPLfunctionsTFSMostPacketDefinition.md)

[CAPL Functions](../CAPLfunctions.md) » [Test Feature Set](CAPLfunctionsTFSOverview.md) » Symbolic definition of MOST messages

# Test Feature Set: Definition of MOST packets

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

Several Test Feature Set functions for processing MOST packets take a string parameter for the specification of packet data. This string description must have one of the following formats:

1. `<Raw data byte description>`
2. `<FBlock>.<Instance>.<Function>.<OpType>`
3. `<FBlock>.<Instance>.<Function>.<OpType>(<Raw data byte description>)`
4. `<FBlock>.<Instance>.<Function>.<OpType>(<High Protocol frame description>)`

A raw data byte description is always enclosed by curly brackets and may contain only hexadecimal digits, blanks or the wildcard symbol "_" as a placeholder for a single hexadecimal digit. Additionally, the wildcard symbol "*" can be used exclusively at the end of a byte description to specify that all data bytes after the last one specified are ignored in a message to be matched. In other words, if there’s no "*" at the end of the description, the length of the data to match must exactly match the length of the description, even if there are single hex digit placeholders at the end. Note, that in most cases it is reasonable to add a "*" at the end, since packets may be filled up with zero bytes at the end to full quadlets size.

Blanks are always ignored and can be used for formatting in order to gain a better readability.

When using a raw data byte description to specify a raw packet (1. form), the first byte in the string describes the first byte in the packet data.

**Example**

```plaintext
// packet must only contain the specified 8 bytes
TestWaitForMostPkt("{ F0 F1 F2 F3 F4 F5 F6 F7}", 500);
// packet must begin with specified 8 bytes; Byte at 5th position may have any value
TestWaitForMostPkt("{ F0 F1 F2 F3 __ F5 F6 F7 *}", 500);
```

FBlock, Instance, Function and OpType can be specified numerically or symbolically based on the function catalog information available (see also Symbolic definition of MOST messages > Specification of names for FBlock, Function and OpType).

**Example**

```plaintext
TestWaitForMostPkt("AudioDiskPlayer.1.DeckStatus.Get", 500);
TestWaitForMostPkt("0x31.0x01.0x200.0x1", 500);
```

When using FBlock, Instance, Function and OpType in conjunction with a raw data byte description for the user data bytes, the first data byte in the raw data description corresponds to the first user data byte (which is the 7. byte in the packet).

**Example**

```plaintext
TestWaitForMostPkt("NetBlock.1.FBlockIDList.Status({ 31 01 *})", 500);
```

When using a High Protocol frame description to specify the user data bytes of a packet, a set of case-sensitive key words is offered to specify the different High Protocol frame types. Each key word has a defined number of allowed parameters that may follow the key word in a bracket-enclosed, comma-separated list. The meaning of each parameter depends on the frame type and position in the message data (for a detailed description of the frame types and parameters, please consult the MOST High Protocol Specification). The following keywords and parameters are recognized:

- REQUEST CONNECTION(Prio, NDF, RevID)
- START CONNECTION(Scale, RevID, PrioAck, NDFAck, AIR)
- READY FOR DATA
- HOLD CONNECTION Tx(Event)
- HOLD CONNECTION Rx(Event)
- END CONNECTION Tx(Event)
- END CONNECTION Rx(Event)
- FRAME ACK(FrAckHi, FrAckLo, BlockCnt)
- REQUEST(FrameID)
- MULTIPLE FRAMES REQUEST(FrameID, FrameID, FrameID, …)
- ADJUST RATE(Operation)
- DATA FRAME(FrAckHi, FrAckLo, `<Raw data byte description>`)
- 0-FRAME(FrAckLo, SegID, Options, BlockCnt)

**Example**

```plaintext
// Test: Start of MHP transmission
// hexadecimal frame parameter values
TestWaitForMostPkt("Navigation.Waypoints.Status(REQUEST CONNECTION(0x7f, 0x30, 0x1))", 100);
// blanks in key words are ignored
TestWaitForMostPkt("Navigation.Waypoints.Status(READYFORDATA)", 100);
// decimal frame parameter values
TestWaitForMostPkt("Navigation.Waypoints.Status(0-FRAME(255, 1, 1, 0))", 100);
```

Each parameter in a list can be set to a numerical value (hex or decimal), or to wildcard value by using "*". Parameters omitted at the end of a list are automatically set to wildcard value.

**Example**

```plaintext
// Wait for 0-FRAME of 200. block
TestWaitForMostPkt("Navigation.Waypoints.Status(0-FRAME(*, *, *, 200))", 100);
```

It is also possible to insert a raw data byte description instead of a direct numerical value at any parameter position in the list. In this case however, this must always be last parameter in the list, since the variable length of a raw byte description prevents any further parameter position matching. In the special case of the DATA FRAME, the last parameter corresponds to the actual data payload of a data frame and must always be described via a raw data byte description. Note that the same rules for wildcards apply here as mentioned above. So if messages longer than specified also should match, it is required to add a "*" wildcard at the end.

**Example**

```plaintext
// Wait for 0-Frame of block with 255 frames and BlockCnt == 5
TestWaitForMostPkt("Navigation.Waypoints.Status(0-FRAME(0xFF, {__ __ 05})", 100);
// Raw data parameter at first position always starts directly after high command byte
TestWaitForMostPkt("Navigation.Waypoints.Status(HOLD CONNECTION Tx({00 83 *})", 100);
// First three bytes of 6. data frame must be 0x20, 0x21, 0x22
TestWaitForMostPkt("Navigation.Waypoints.Status(DATA FRAME(0x06, 0xFF, {20 21 22 *})", 100);
```

Note, that the TelID also matters for matching incoming packets. DATA FRAME and 0-FRAME specifications only match packets with TelID = 8, whereas all other frame types only consider packets with TelID = 9.

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
