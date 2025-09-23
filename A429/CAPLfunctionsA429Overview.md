[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/CAPLfunctionsA429Overview.md)

## A429 CAPL Functions

[CAPL Functions](../CAPLfunctions.md) » A429 CAPL Functions

**Valid for**: CANoe DE • CANoe4SW DE

### Functions

- [a429CalcBitLength](Functions/CAPLfunctionA429CalcBitLength.md): Returns the bit length for a given channel.
- [a429CheckParity](Functions/CAPLfunctionA429CheckParity.md): Checks the parity of an ARINC word.
- [a429GetBitLength](Functions/CAPLfunctionA429GetBitLength.md): Returns the length of an erroneous measured bit in an Rx error.
- [a429GetConfiguration](Functions/CAPLfunctionA429GetConfiguration.md): Returns the current channel configuration settings.
- [a429GetErrorPosition](Functions/CAPLfunctionA429GetErrorPosition.md): Gets the error position of a Rx error.
- [a429InitPayload](Functions/CAPLfunctionA429InitPayload.md): Initialize the payload of an existing a429word.
- [a429ResetEx](Functions/CAPLfunctionA429ResetEx.md): Re-initialize a selected channel with current channel parameters.
- [a429SetConfiguration](Functions/CAPLfunctionA429SetConfiguration.md): Sets the current channel configuration settings.
- [a429SetGap](Functions/CAPLfunctionA429SetGap.md): Sets the selector **gap** of an ARINC word.
- [a429SetParity](Functions/CAPLfunctionA429SetParity.md): Sets the selector **parity** of an ARINC word.
- [a429SetScheduleTx](Functions/CAPLfunctionA429SetScheduleTx.md): Prepares an ARINC word to be transmitted cyclically by means of the hardware scheduling support.
- [a429StopTx](Functions/CAPLfunctionA429StopTx.md): Stops the cyclic transmission of an ARINC word.
- [a429Transmit](Functions/CAPLfunctionA429Transmit.md): Triggers the transfer of several ARINC words to the network interface at once.
- [output](Functions/CAPLfunctionA429output.md): Transmits an ARINC word to the network interface.

### Event Procedures

- [on a429error](EventProcedures/CAPLfunctionA429OnA429Error.md): Receives an ARINC error event.
- [on a429word](EventProcedures/CAPLfunctionA429OnA429Word.md): Receives an ARINC word event.
- [on a429worderror](EventProcedures/CAPLfunctionA429OnA429WordError.md): Receives an ARINC word error event.

[Declaration of ARINC Words](CAPLfunctionsA429DefineARINCword.md) • [ARINC Word Selectors](CAPLfunctionsA429Selectors.md) • [Scheduling an ARINC Word](CAPLfunctionsA429Scheduling.md) • [Reconfigure a Channel](CAPLfunctionsA429ChannelReconfig.md)
