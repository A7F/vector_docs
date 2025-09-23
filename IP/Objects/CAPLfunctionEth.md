# Eth

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

Eth `<Ethernet Channel Number>`;

## Description

Can be used to get the status and statistics of the Ethernet link.

Use [ethResetStatistics](../Functions/CAPLfunctionEthResetStatistics.md) to reset the statistics values.

## Parameters

- **Ethernet Channel Number**: Channel number 1..32.

## Selectors

Note: The following selectors are only valid for **channel-based access**.

- **status**:
  - 0 – Link down
  - 1 – Link up
  - Type: long
  - Access Limitation: Read only

- **bitrate**:
  - Bitrate in kBit/sec
  - Type: dword
  - Access Limitation: Read only

- **TxBitrate**:
  - Current TX bitrate in [kBit/sec]
  - Type: dword
  - Access Limitation: Read only

- **RxBitrate**:
  - Current RX bitrate in [kBit/sec]
  - Type: dword
  - Access Limitation: Read only

- **TxPacketRate**:
  - Current TX packet rate [pkt/sec]
  - Type: dword
  - Access Limitation: Read only

- **RxPacketRate**:
  - Current RX packet rate [pkt/sec]
  - Type: dword
  - Access Limitation: Read only

- **TxPacketCount**:
  - Number of transmitted Ethernet packets
  - Type: qword
  - Access Limitation: Read only

- **RxPacketCount**:
  - Number of received Ethernet packets
  - Type: qword
  - Access Limitation: Read only

- **TxByteCount**:
  - Number of transmitted bytes
  - Type: qword
  - Access Limitation: Read only

- **RxByteCount**:
  - Number of received bytes
  - Type: qword
  - Access Limitation: Read only

- **TxErrorCount**:
  - Number of transmitted error packets
  - Type: dword
  - Access Limitation: Read only

- **RxErrorCount**:
  - Number of received error packets
  - Type: dword
  - Access Limitation: Read only

- **SQI**:
  - Current Signal Quality Indicator:
    - 0 – Error Occurring
    - 1 – No Margin
    - 2 – Marginal
    - 3 – Acceptable
    - 4 – Good
    - 5 – Excellent
    - 6 - not available
  - Type: dword
  - Access Limitation: Read only

## Example

```plaintext
switch(Eth1.status)
{
  case 0:
    write("Ethernet link on Eth1 is down" );
    break;
  case 1:
    write("Ethernet link on Eth1 is up with %dMBit/sec", Eth1.bitrate/1000);
}
```

See Also: [Concept Link](javascript:void(0);)
