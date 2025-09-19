# `<OnAfdxPacket>` (Callback)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This callback must be implemented in the CAPL program by the user to use the function [AfdxRegisterReceiveCallback](../Functions/CAPLfunctionAfdxRegisterReceiveCallback.md).

## Function Syntax

```plaintext
void <OnAfdxPacket>( long dir, long line, int64 timestamp, long bag, long afdxFlags, long packet );
```

## Description

This callback is called when a registered AFDX packet is received.

## Parameters

- **dir**: Direction of the packet or fragment.
  - 0: Rx
  - 1: Tx
- **line**: Line of the packet or fragment.
  - 0: LineUndefined (e.g. for reassembled packets)
  - 1: LineA
  - 2: LineB
  - 3: LineAB
- **timestamp**: Time stamp of the packet or fragment in ns.
- **bag**: Time difference since last packet of this Virtual Link in ms.
- **afdxFlags**: 
  - **status info**
    - bit 0: This packet was received from Line-B.
    - bit 1: This packet is redundant.
    - bit 2: This packet is fragmented.
    - bit 3: This packet is from a SAP port.
  - **error info**
    - bit 4: Packet was received in wrong interface (Line-A versus Line-B).
    - bit 5: Packet has an invalid Ethernet packet content.
    - bit 6: Packet has an invalid sequence number.
    - bit 7: Packet has a time-out on redundancy reception.
    - bit 8: Packet has encountered a fragmentation error.
    - bit 9: Packet has protocol errors on higher protocol level.
    - bit 10: Packet has been reassembled.
- **packet**: Handle of the received packet or fragment.

## Return Values

—

## Example

**Node System - preStart in CAPL Browser**

```plaintext
on preStart
{
  long result;
  // register a callback to receive AFDX packets in general
  result = AfdxRegisterReceiveCallback("OnAfdxPacket");
}
```

**Node Callback Function in CAPL Browser**

```plaintext
void OnAfdxPacket(long dir, long line, int64 time, long bag, long afdxFlags, long packet )
{
  // check if the packet has been sent by the node
  if (dir == TX)
  {
    sysSetVariableLong(sysvar::NodeA::TxPacketCount,(SysGetVariableLong(sysvar::NodeA::TxPacketCount) + 1));
  } // if
}
```
