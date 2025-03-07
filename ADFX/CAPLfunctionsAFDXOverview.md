# AFDX CAPL Functions

[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/CAPLfunctionsAFDXOverview.md)

**CAPL Functions** » AFDX CAPL Functions

**Valid for**: CANoe DE • CANoe4SW DE

**ON THIS PAGE:**

- [A664 Functions (only CANalyzer, CANoe DE, CANoe:lite DE)](#A664)
- [A664 Handler (only CANalyzer, CANoe DE, CANoe:lite DE)](#A664-Handler)
- [AFDX Interaction Layer](#AFDXIL)
- [Callback Functions](#Callback)
- [DB API](#DB_API)
- [General Functions](#GeneralFunctions)
- [Packet API](#PacketAPI)
- [Signal API](#SignalAPI)

## A664 Functions

The following CAPL functions are based on native CAPL. These are the recommended functions to use for CAPL programming.

### A664 Functions (only CANalyzer, CANoe DE, CANoe:lite DE) [▲ back](#Shortcuts)

- **A664CloseProxyPort**: Method to close a specific socket port, which was generated using a664InitProxyPort.
- **A664GetFunctionalStatus**: This function returns the Functional Status (FS) of an AFDX-PDU (FDS).
- **A664InitICMP**: The complete Ethernet and IP headers of an AFDX packet are consistently set based on the given parameters.
- **A664InitMessage**: The complete Ethernet, IP- and UDP headers for an AFDX message are consistently set based on the given parameters. The payload area is initialized with 0.
- **A664InitPayload**: The payload section (excluding sequence number) of an AFDX message is set using the current Tx-values of the internal signal list (CANdb++).
- **A664InitProxyPort**: Open a windows socket based on a network adapter characterized by the ipAddr parameter and using the specified UDP-port.
- **A664isICMP**: This function returns the ICMP type and code for a packet. The intended use case is a check for an expected ICMP packet in an on-handler.
- **A664MsgConfig**: This function triggers the scheduling of the message aMessage. The message is either scheduled once or periodic.
- **A664ResizeMessage**: The message object’s payload area is resized to match the new payload size.
- **A664SetChecksum**: This function calculates and sets the checksum in the specified aFrame according to the defined checksum rule.
- **A664SetFunctionalStatus**: This function sets the Functional Status (FS) of a AFDX-PDU (FDS) (available only in PDU-mode).
- **A664SetStringSignal**: This function can be used to set a string-signal within a specific a664Message (form 2) or to set the Tx-signal of the CANoe DE product subsystem (form 1).
- **A664TriggerFrame**: This function triggers the transmission of a single frame <aFrame> either immediately or respecting the BAG.
- **A664TriggerMessage**: This function triggers the scheduling of the message "aMessage". The message is either scheduled once or periodic.
- **A664VLConfig**: Configure a Virtual-Link for a given a664Frame or a664Message.
- **Copy Operator**: The copy operator allows to copy a664Message object and a664Frame object combinations.
- **Output**: This function outputs the object from the program block of the analysis branch.

### A664 Handler/Event Procedures (only CANalyzer, CANoe DE, CANoe:lite DE)

- **on a664Frame**: The event procedure **on a664Frame** is called on every AFDX packet if certain conditions are fulfilled.
- **on a664Message**: The event procedure **on a664Message** is called on every AFDX message if certain conditions are fulfilled.

## AFDX Interaction Layer

The following functions are not recommended any more. Use native CAPL programming (A664) above instead.

The AFDX Interaction Layer (AFDX IL) enables the simulation of AFDX nodes with CAPL and allows sending and receiving individual AFDX packets. For addressing parts of a frame so-called tokens are used.

- [raw Ethernet packet](../../CANoeCANalyzer/AFDX/protocols/afdxProtocolEthernet.md): "eth"
- [IPv4 frame](../../CANoeCANalyzer/AFDX/protocols/afdxProtocolIPv4.md): "ipv4"
- [UDP frame](../../CANoeCANalyzer/AFDX/protocols/afdxProtocolUDP.md): "udp"
- [AFDX frame](../../CANoeCANalyzer/AFDX/protocols/afdxProtocolAfdx.md): "afdx"

For more convenience in the programming environment a [CAPL include file](../../Shared/CAPL/IncludeFiles/IncludeFiles.md) is provided.

To use the CAPL functions the [AFDX_IL.DLL](../../CANoeCANalyzer/AFDX/afdxIL/afdxILInclude.md) must be included.

## Callback Functions [▲ back](#Shortcuts)

- **<OnAfdxError>**: CAPL callback to handle AFDX error events.
- **<OnAfdxPacket>**: CAPL callback to receive data of AFDX packets.

## DB API [▲ back](#Shortcuts)

- **AfdxGetDBAttrAsString**: Retrieves a message attribute value in string representation from a given message ID.
- **AfdxGetDBAttrValue**: Retrieves the value of a specific attribute of a dedicated message if the attribute is not of type string.
- **AfdxGetDBMessageName**: Retrieves the message name from database from a given message ID if it is defined there.

## General Functions [▲ back](#Shortcuts)

- **AfdxGetLastError**: Gets the last error code.
- **AfdxGetLastErrorText**: Gets the description of the last error code.
- **AfdxSetErrorHandler**: Registers a CAPL callback to handle AFDX error events.
- **AfdxSetVerbosity**: Sets the verbosity level of the AFDX IL.

## Packet API [▲ back](#Shortcuts)

- **AfdxCompletePacket**: Completes an AFDX packet for sending.
- **AfdxDeregisterReceiveCallback**: Deregisters a previous installed CAPL callback.
- **AfdxGetMessageId**: Gets the ID of a message.
- **AfdxGetMessageName**: Gets the name of a message.
- **AfdxGetPacketData**: Copies the packet content to a local buffer.
- **AfdxGetTokenData**: Gets the data of a token.
- **AfdxGetTokenInt**: Gets the integer value of a token.
- **AfdxGetTokenInt64**: Gets the 64 bit integer value of a token.
- **AfdxGetTokenLengthBit**: Gets the length of a token in bit.
- **AfdxGetTokenReal**: Gets the float or double value of a token.
- **AfdxGetTokenString**: Gets the string value of a token.
- **AfdxInitPacket**: Creates a new AFDX packet.
- **AfdxInitProtocol**: Initializes a protocol for an AFDX packet.
- **AfdxInitSchedule**: Initializes the scheduled transmission of the specified message during the start phase of the measurement.
- **AfdxIsPacketValid**: Checks if an AFDX packet has protocol errors.
- **AfdxIsReceiveCallbackRegistered**: Determines if a CAPL callback with this name is installed.
- **AfdxOutputPacket**: Sends an AFDX packet.
- **AfdxOutputPacketRaw**: Sends a raw AFDX packet.
- **AfdxOutputPacketWithSignals**: Sends a message and automatically updates the payload with the current Tx-signal values of the SignalServer.
- **AfdxRegisterReceiveCallback**: Registers a CAPL callback function to receive AFDX packets.
- **AfdxReleasePacket**: Deletes an AFDX packet.
- **AfdxRemoveToken**: Removes a token from a protocol header.
- **AfdxResizeToken**: Modifies the length of a token.
- **AfdxSetTokenData**: Sets the data of a token.
- **AfdxSetTokenInt**: Sets the integer value of a token.
- **AfdxSetTokenInt64**: Sets the 64 bit integer value of a token.
- **AfdxSetTokenReal**: Sets the float or double value of a token.
- **AfdxSetTokenString**: Sets the string value of a token.

## Signal API [▲ back](#Shortcuts)

If signals of messages are defined in an AFDX database, they may be accessed via their defined signal names with these functions or by an offset within the payload if no database information is available.

**Read signals from AFDX message payload according to their data type.**

- **AfdxGetSignalBool**: Read boolean.
- **AfdxGetSignalInt**: Read integer value (32 bit).
- **AfdxGetSignalInt64**: Read integer value (64 bit).
- **AfdxGetSignalOpaque**: Read opaque value.
- **AfdxGetSignalReal**: Read real/float value.
- **AfdxGetSignalStatus**: Read frame data set (FDS) status.
- **AfdxGetSignalString**: Read string type.

**Write signals in AFDX message payload according to their data type.**

- **AfdxSetSignalBool**: Write boolean.
- **AfdxSetSignalInt**: Write integer value (32 bit).
- **AfdxSetSignalInt64**: Write integer value (64 bit).
- **AfdxSetSignalOpaque**: Write opaque value.
- **AfdxSetSignalReal**: Write real/float value.
- **AfdxSetSignalStatus**: Write frame data set (FDS) status.
- **AfdxSetSignalString**: Write string type.

[AFDX Error Codes](CAPLfunctionsAFDXErrorCodes.md) • [AFDX Selectors](CAPLfunctionsAFDXSelectors.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)