[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/CAPLfunctionsLINHardwareConfiguration.md)

**CAPL Functions** » [LIN](CAPLfunctionsLINOverview.md) » Hardware Configuration

# LIN: Hardware Configuration

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE

On selecting a LIN channel in the hardware configuration dialog, important parameters for the connected hardware such as hardware type and firmware version are displayed on the right. Underneath further hardware settings are displayed:

- Protocol
- Baudrate
- Master Mode
- Master Resistor

The values for these settings are extracted from the LIN database assigned to the channel being displayed. If no database is currently assigned or the database settings should be overwritten, you can select these settings manually.

To overwrite the database settings, please activate the **Override DB settings** option.

Certain network parameters depend on the used protocol version:

## LIN 1.x

- Wakeup frame retransmission delay (‘ttobrk’): 125 bit times
- Number of Wakeup frame retransmissions: 3
- Length of Wakeup frame: 8 bit times
- Wakeup delimiter length: 4 bit times
- Byte order: Little-Endian

## LIN 2.x

- Wakeup frame retransmission delay (‘ttobrk’): 150 ms
- Number of Wakeup frame retransmissions: 3
- Length of Wakeup frame: 1000 µs
- Wakeup delimiter length: 100 ms
- Byte order: Little-Endian

## OEM variant

- Wakeup frame retransmission delay (‘ttobrk’): 50 ms
- Number of Wakeup frame retransmissions: 3
- Length of Wakeup frame: 600 µs
- Wakeup delimiter length: 35 ms
- Byte order: Big-Endian

## SAE-J2602

- Wakeup frame retransmission delay (‘ttobrk’): 150 ms
- Number of Wakeup frame retransmissions: 3
- Length of Wakeup frame: 1000 µs
- Wakeup delimiter length: 100 ms
- Byte order: Little-Endian

## Cool-LIN

- Settings identical LIN 1.x

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
