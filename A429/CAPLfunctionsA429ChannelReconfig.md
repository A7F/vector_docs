# Reconfigure a Channel

[CAPL Functions](../CAPLfunctions.md) » [A429](CAPLfunctionsA429Overview.md) » Reconfigure a Channel

**Valid for**:  CANoe DE • CANoe4SW DE

For channel configuration purposes a specific variable type **a429settings** is provided. Channel configuration settings may be accessed via the functions [a429GetConfiguration](Functions/CAPLfunctionA429GetConfiguration.md), [a429SetConfiguration](Functions/CAPLfunctionA429SetConfiguration.md) and [a429ResetEx](Functions/CAPLfunctionA429ResetEx.md).

Note that the configuration settings may overwrite settings in the [hardware configuration dialog](../../CANoeCANalyzer/A429/windows/hwConfig/hwConfigA429PageA429.md).

## Selectors

- **Bitrate**: channel bitrate (Bit/s)
  - Tx: This bitrate has to be used for transmitting ARINC words.
    - Value range: 10500..16000; 90000..110000
  - Rx: This is the expected bitrate for any traffic on this channel.
    - Value range: 0 (AUTO); 10000..120000
    - If 0 is provided the bitrate is detected automatically. The detection area is limited by **RxMinBitrate** and **RxMaxBitrate**.
  - Type: dword

- **RxMinBitrate**: Lowest allowed bitrate (Bit/s)
  - Tx: no meaning
  - Rx: If the detected bitrate is lower an error is generated; value range: 10000..120000
  - Type: dword

- **RxMaxBitrate**: Highest allowed bitrate (Bit/s)
  - Tx: no meaning
  - Rx: If the detected bitrate is higher an error is generated; value range: 10000..120000
  - Type: dword

- **MinGap**: Minimum allowed distance between two consecutive ARINC words (1/8 fractions of a bit time)
  - Tx: The defined gap time precedes every ARINC word
  - Rx: If the time between two consecutive ARINC words falls below that value, an error is generated.
  - Value range: 1..1024
  - Type: dword

- **Parity**: Parity support
  - Tx: parity bit in ARINC word may be modified according to these settings
  - Rx: parity checking is done according to these settings
  - Value range:
    - 0: use channel configuration (default)
    - 1: disable hardware parity support
    - 2: odd parity
    - 3: even parity
  - Type: dword

- **Flags**: Channel direction flags (read only)
  - Value range:
    - 0: unknown (for "Simulated bus");
    - 1: Tx
    - 2: Rx
  - Type: dword

In order to reconfigure a channel the function [a429SetConfiguration](Functions/CAPLfunctionA429SetConfiguration.md) has to be called successfully. The configuration is applied with [a429ResetEx](Functions/CAPLfunctionA429ResetEx.md).

### Example

```plaintext
variables {
  a429Settings mySet;
  mySet.Bitrate = 0;
  mySet.RxMinBitrate = 99000;
  mySet.RxMaxBitrate = 101000;
  mySet.MinGap = 32;
  mySet.Parity = a429OddParity;
  mySet.Flags = 0;
}

on key 'c' {
  a429SetConfiguration (1, mySet);
  a429ResetEx (1);
}
```
