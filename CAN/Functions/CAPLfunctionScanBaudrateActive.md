# ScanBaudrateActive

**Valid for:** CANoe DE • CANoe:lite DE

## Use Case

The applied baudrate on a real network should be determined on which NO communication exists. In this case CANoe is an active participant - Transmitter - on the network.

## Function Syntax

```
long ScanBaudrateActive( dword channel, dword messageID, double firstBaudrate, double lastBaudrate, dword timeout);
```

## Description

The function determines the baudrate for the given channel. Result of the function is written into the Write Window.

The baudrate scanner checks different baudrates and tries to send a message through the given channel. The function is finished if the message was sent successfully and the baudrate was determined. If a wrong baudrate is present, the other power supply takers cannot receive the message. CANoe as the transmitter does not receive an acknowledge and sends an Error Frame. In this case the next baudrate of the baudrate range is checked.

**Note:** CAN.INI file settings for the baudrate scanner:

```
[BaudrateScanner]
Dlc=8
DisplayBaudrateList=0
```

- **Dlc:** DLC of the message sent by the scanner. Default value: 8
- **DisplayBaudrateList:** If this value is set to 0 the baudrate scanner stops after finding the first baudrate. If the value is non-zero the scanner checks all baudrates and displays a list of values at the end. Default value: 0

## Parameters

- **channel**: Channel number. (1,..,32)
- **messageID**: ID of the message that the scanner will send to detect the baudrate. The DLC of the message is always 8.
- **firstBaudrate / lastBaudrate**: Baudrate range to scan.
  - If both values are set to zero the scanner checks the most commonly used baudrates: 33.333, 50.0, 83.333, 100.0, 125.0, 250.0, 500.0, 1000.0 [kBaud]
  - If both values are the same but not zero the scanner multiplies the baudrate with a given factor (Value range 0.25-5.0). The factor is changed with steps of 0.25.
  - If both values are different, all possible baudrate values in the range are scanned. The incremental step in the range is 1.5%.
- **timeout**: Period of time [ms] the scanner waits when the message is sent.

## Return Values

Returns 0 if the scan function was successfully started. Otherwise the return value is non-zero.

## Example

—

[ScanBaudratePassive](CAPLfunctionScanBaudratePassive.md)
