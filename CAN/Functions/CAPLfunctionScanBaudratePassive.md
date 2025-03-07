[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionScanBaudratePassive.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » ScanBaudratePassive

# ScanBaudratePassive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Use Case

The applied baudrate on a real network should be determined on which communication exists. In this case CANoe is a passive participant - receiver - on the network and it is connected about a Y cable to the network.

## Function Syntax

```
long ScanBaudratePassive( dword channel, dword messageID, double firstBaudrate, double lastBaudrate, dword timeout, dword bAcknowledge);
```

## Description

Baudrate scanner checks different baudrates and tries to receive a message on the channel. Function starts the scan and detects the baudrate on the given channel. Result of the function is written into the Write Window.

If a wrong baudrate is present, CANoe cannot receive messages and sends an Error Frame, which can be put on the bus using the parameter **bAcknowledge**.

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
- **messageID**: ID of the message that the scanner will receive to detect the baudrate. If this value is 0xffff the scanner will receive all the messages on the channel.
- **firstBaudrate / lastBaudrate**: Baudrate range to scan.
  - If both values are set to zero the scanner checks the most commonly used baudrates: 33.333, 50.0, 83.333, 100.0, 125.0, 250.0, 500.0, 1000.0 [kBaud]
  - If both values are the same but not zero the scanner multiplies the baudrate with a given factor (Value range 0.25-5.0). The factor is changed with steps of 0.25.
  - If both values are different, all possible baudrate values in the ranged are scanned. The incremental step in the range is 1.5%.
- **timeout**: Period of time [ms] the scanner waits when the message is sent.
- **bAcknowledge**: [Acknowledge mode](../../../CANoeCANalyzer/Ribbon/Hardware/NetworkHardware/NetworkHardwareCANControllerConfiguration.md) on (1)/off (0). If a wrong baudrate is present, CANoe cannot receive messages and sends an Error Frame, which can be put on the bus using the parameter **bAcknowledge**. The parameter serves for the fact that CANoe - as a passive receiver - can participate indirectly in the network communication by sending an Error Frame. The parameter does not change the acknowledge settings of the **Hardware Configuration** dialog. The parameter has an effect only during runtime of the function.

## Return Values

Returns 0 if the scan function was successfully started. Otherwise the return value is non-zero.

## Example

—

[ScanBaudrateActive](CAPLfunctionScanBaudrateActive.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)