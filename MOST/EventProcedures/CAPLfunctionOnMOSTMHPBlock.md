[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTMHPBlock.md)

**CAPL Functions** » **MOST** » **OnMostMHPBlock**

# OnMostMHPBlock

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

**Note**  
`OnMostMHPBlock` can only be used in the **Measurement Setup** and should be inserted under the item "Callback function". For simulation of a MOST High connection sender and receiver in CAPL, the MOST High DLL can be used. The DLL is located in the Exec32 folder of the MOST High Demos.

## Function Syntax

```plaintext
long OnMostMHPBlock(long sourceDevID, long destDevID, long fBlockID, long instID, long functionID, long opType);
```

## Description

The event procedure is called up as soon as a block from a MOST High connection has been fully transmitted. Within this event procedure the following functions are available:

- `long mostMHPBlockGetData(byte buffer[], long bufferSize)`

  Copies the reference data of the block in a provided buffer.  
  **Parameter**:  
  buffer (buffer for the data bytes)  
  bufferSize (size of the buffer)  
  **Returns**:  
  Number of data bytes copied

- `long mostMHPBlockIsSpy()`

  Indicates whether the block was made up of Spy messages.  
  **Parameter**:  
  None  
  **Returns**:  
  0: Comprised of node messages  
  1: Comprised of Spy messages

- `long mostMHPBlockNumberOfFrames()`

  Provides the number of Data Frames of the block.  
  **Parameter**:  
  None  
  **Returns**:  
  Number of actual Data Frames

- `long mostMHPBlockNumberOfFramesIndicated()`

  Provides the number of Data Frames of the block that it should have according to the 0-frame.  
  **Parameter**:  
  None  
  **Returns**:  
  Number of Data Frames

- `long mostMHPBlockSize()`

  Provides the size of the block.  
  **Parameter**:  
  None  
  **Returns**:  
  Number of data bytes (reference data only)

- `long mostMHPBlockTransportMode()`

  Provides the transmission mode of the block.  
  **Parameter**:  
  None  
  **Returns**:  
  1: Transmission on the control channel  
  2: Transmission on the asynchronous channel

- `long mostMHPBlockCnt()`

  Provides the sequence number of the block.  
  **Parameter**:  
  None  
  **Returns**:  
  Cnt field of the 0-frame (see MHP specification)

- `long mostMHPBlockOptions()`

  Provides the options for the transmission of the block.  
  **Parameter**:  
  None  
  **Returns**:  
  Options field of the 0-frame (see MHP specification)

- `long mostMHPBlockSegID()`

  Provides the segmentation ID of the block.  
  **Parameter**:  
  None  
  **Returns**:  
  Options field of the 0-frame (see MHP specification)

The functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md), and [mostEventTimeNS](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

## Parameters

- **sourceDevID**: Address of the transmitter
- **destDevID**: Address of the receiver
- **fBlockID**: FBlockID of the receiver
- **instID**: Instance ID of the receiver
- **functionID**: FunctionID of the receiver
- **opType**: OpType of the receiver

## Return Values

The return value determines whether the MHP block event is relayed to the next function block in the Measurement Setup (e.g., a Trace Window).

- **0**: No relay
- **1**: Relay

## Example

The example shows how the data of a block can be written to a file. The file (`fileHandle` variable) must be opened in advance. The block event is relayed by the "return 1" instruction to the next function block in the Measurement Setup.

```plaintext
const long blockBufferSize = 64*1024;
long OnMostMHPBlock (long sourceDevID, long destDevID, long fBlockID, long instID,
long functionID, long opType)
{
   // Prepare a data buffer
   byte buffer[blockBufferSize];
   long byteCount;
   // Get data of the MHPBlock
   mostMHPBlockGetData(buffer, blockBufferSize);
   // Write data to the file
   byteCount = (mostMHPBlockSize() < blockBufferSize) ?
   mostMHPBlockSize() :
   blockBufferSize;
   fileWriteBinaryBlock(buffer, byteCount, fileHandle);
   // Forward MHPBlock to the next CAPL node
   return 1;
}
```

[**MOST High Protocol: Simulation of Sender and Receiver**](../../../CANoeCANalyzer/MOST/MOSTHighProtocolSimulation.md) • [OnMostMHPPacket](CAPLfunctionOnMOSTMHPPacket.md) • [OnMostMHPError](CAPLfunctionOnMOSTMHPError.md) • [mostMHPBlockSetTraceColors](../Functions/CAPLfunctionMOSTMHPBlockSetTraceColors.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
