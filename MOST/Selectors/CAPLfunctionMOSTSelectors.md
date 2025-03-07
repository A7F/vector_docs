# MOST Selectors

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Selectors/CAPLfunctionMOSTSelectors.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » MOST Selectors

Valid for: CANoe DE

## mostMessage and mostAMSmessage Selectors

- **ACK**: [Acknowledgment information](../../../CANoeCANalyzer/Windows/Trace/TraceWindowMOSTAckNackInformation.md)  
  Range: 0...0xFF  
  Access: read only

- **Arbitration**: Bus arbitration bytes  
  Range: 0...0xFFFFFFFF  
  Access: read only, Spy

- **DA**: Destination address  
  Range: 0...0xFFFF  

- **DIR**: Direction of transmission  
  Range: Tx, Rx, TxRequest  

- **FBlockID**: Function block identifier  
  Range: 0...0xFF  

- **FunctionID**: Function identifier  
  Range: 0...0xFFF  

- **ID**: Message ID (CANdb lookup key)  
  Range: 0...0xFFFFFF  
  Access: obsolete!

- **InstanceID**: Instance identifier  
  Range: 0...0xFF  

- **SA**: Source address  
  Range: 0...0xFFFF  

- **OpType**: Operation type  
  Range: 0...0xF  

- **PIndex**: PIndex is a node-based counter (1 byte) which increments per message sent. All low-level retries of a message have the same PIndex.  
  Range: 0..0xFF  
  Access: read only, Spy

- **MsgChannel**: Transmission channel  
  Range: 1...16  

- **MsgOrigTime**: Unsynchronized hardware time stamp (unit: 10 µs)  
  Access: read only

- **Most_IsSpy**: Message was received by: 1: Spy 0: Node  
  Range: 0, 1  
  Access: read only

- **Most_RType**: Message types:  
  When receiving always **Normal**, other message types are received with mostRawMessage.  
  When applying a mostMessage variable the type can be set to Normal, RemRead, RemWrite, Alloc, Dealloc or GetSource.  
  Range: 0...0x5  

- **Most_State**: [Status information](../../../CANoeCANalyzer/Windows/Trace/TraceWindowMOSTStatusInformation.md)  
  Range: 0...0xFF  
  Access: read only

- **Most_TelID**: TelID  
  Range: 0...0xF  

- **Time**: Synchronized time (unit: 10 µs)  
  Access: read only

These selectors are only valid for **mostAMSMessage**

- **BYTE(idx)**: Provides access to the data bytes of the complex MOST message. (BYTE(0) is the first parameter byte)  
  Range: 0 ≤ idx ≤ 65534  
  Valid Values: 0..0xFF  

- **DLC**: Data length code (Number of user data bytes for mostAMSMessages)  
  Range: 0..65535  

These selectors are only valid for **mostMessage**

- **Arbitration**: Bus arbitration bytes  
  Range: 0...0xFFFFFFFF  
  Access: read only, Spy

- **BYTE(idx)**: Provides access to the data bytes of the MOST frame. (BYTE(0) is the first byte behind the TelLen)  
  Range: 0 ≤ idx ≤ 11  
  Valid Values: 0...0xFF  

- **CAck**: Returns the CRC acknowledge code  
  Range: 0...0xFF  
  Access: read only, Spy, MOST150 only  
  Values: 0x00: No Response, 0x01: CRC error, 0x04: OK

- **DLC**: Data length code (TelLen)  
  Range: 0...45  

- **Most_TelID**: TelID  
  Range: 0...0xF  

- **MsgCRC**: CRC code  
  Range: 0...0xFFFF  
  Access: read only, Spy

- **Most_RType**: Message types:  
  When receiving always **Normal**, other message types are received with mostRawMessage.  
  When applying a mostMessage variable the type can be set to Normal, RemRead, RemWrite, Alloc, Dealloc or GetSource.  
  Range: 0...0x5  
  Access: MOST25 only

- **PAck**: Returns the preemptive acknowledge code  
  Range: 0...0xFF  
  Access: read only, Spy, MOST150 only  
  Values: 0x00: No Response, 0x01: Buffer full, 0x04: OK

- **PIndex**: PIndex is a node-based counter (1 byte) which increments per message sent. All low-level retries of a message have the same PIndex.  
  Range: 0..0xFF  
  Access: read only, Spy, MOST150 only

Example:  
Press <Ctrl>+<W> or select **Signal insertion from MOST function catalog...** from the shortcut menu to open a selection dialog listing all messages and their parameters from the function catalog for selection.  
This includes all non-nested parameters in the user data with constant width and constant position.  
In this context, the parameter name is inserted into the program text as a selector.

## mostRawMessage Selectors

- **ACK**: [Acknowledgment information](../../../CANoeCANalyzer/Windows/Trace/Columns/TraceColumnsMOST.md)  
  Range: 0...0xFF  
  Access: read only, Spy

- **Arbitration**: Bus arbitration bytes  
  Range: 0...0xFFFFFFFF  
  Access: read only, Spy

- **BYTE(idx)**: Provides the access to the data bytes of the MOST frame. 0 ≤ idx ≤ 16  
  Range: 0...0xFF  

- **DA**: Destination address  
  Range: 0...0xFFFF  

- **DIR**: Direction of transmission  
  Range: Tx, Rx, TxRequest  

- **MsgChannel**: Transmission channel  
  Range: 1...16  

- **MsgCRC**: CRC code  
  Range: 0...0xFFFF  
  Access: read only, Spy

- **MsgOrigTime**: Unsynchronized hardware time stamp (unit: 10µs)  
  Access: read only

- **Most_IsSpy**: Message was received by: 1: Spy 0: Node  
  Range: 0, 1  
  Access: read only

- **Most_RType**: Message type (Normal, RemRead, RemWrite, Alloc, Dealloc, GetSource)  
  Range: 0...5  

- **Most_State**: [Status information](../../../CANoeCANalyzer/Windows/Trace/TraceWindowMOSTStatusInformation.md)  
  Range: 0...0xFF  
  Access: read only

- **SA**: Source address  
  Range: 0...0xFFFF  

- **Time**: Synchronized time (unit: 10µs)  
  Access: read only

Byte contents of mostRawMessages (see data sheet of MOST transceiver OS8104):

- **Byte 0**: rsvd
- **Byte 1**: MAP
- **Byte 2**: LENGTH
- **Byte 3**: D0
- **Byte 4**: D1
- **Byte 5**: D2
- **Byte 6**: D3
- **Byte 7**: D4
- **Byte 8**: D5
- **Byte 9**: D6
- **Byte 10**: D7
- **Byte 11**: rsvd
- **Byte 12**: rsvd
- **Byte 13 ... 16**: rsvd

## mostLightLockError Selectors

- **Most_Light**: Light state of controller  
  Range: 0, 1  
  Access: read only, mostLightLockError

- **Most_Lock**: Lock state of controller  
  Range: 0, 1  
  Access: read only, mostLightLockError

- **Most_Error**: 0: as long as lock exists 1: as soon as lock does not exists  
  Range: 0, 1  
  Access: read only, mostLightLockError

- **Time**: Synchronized time (unit: 10µs)  
  Access: read only

- **MsgOrigTime**: Unsynchronized hardware time stamp (unit: 10µs)  
  Access: read only

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)