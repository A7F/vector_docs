[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANDisturbance/Classes/CAPLfunctionCanDisturbanceSequence.md)

## CAPL Functions » CAN Disturbance Interface » Classes » Class: CanDisturbanceSequence

### Class: CanDisturbanceSequence

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

An object of this class represents a user defined sequence. A sequence can contain up to 4096 segments. A segment can be added by using the function [AppendToSequence](../Functions/CAPLfunctionCanDisturbanceSequenceAppendToSequence.md). To clear the current configured sequence the [Clear](../Functions/CAPLfunctionCanDisturbanceSequenceClear.md) method can be used. The [ToString](../Functions/CAPLfunctionCanDisturbanceSequenceToString.md) method can be used to write the current configured sequence to a text buffer or a test report.

### Methods

- [AppendToSequence](../Functions/CAPLfunctionCanDisturbanceSequenceAppendToSequence.md)
- [Clear](../Functions/CAPLfunctionCanDisturbanceSequenceClear.md)
- [ToString](../Functions/CAPLfunctionCanDisturbanceSequenceToString.md)

### Attributes

You can access control information of a **CanDisturbanceSequence** object with the following attributes:

- **SegmentCount**: The count of the segments currently added to the sequence.  
  Type: `dword`  
  Access Limitations: read-only

### Example

```plaintext
CanDisturbanceSequence       sequence; //Object of sequence
dword                        deviceID; //Device Id of disturbance interface
char                         buffer[1024]; //text buffer for ToString method

deviceID = 1;

//clear the sequence
  if(sequence.SegmentCount > 0)
{
  sequence.Clear();
}
//configure a sequence 320 FPGA ticks long and send a recessive bit at the Ack slot bit on the bus. A FPGA tick is 6.25 ns long, which leads to a bit time of 2 µs
result = sequence.AppendToSequence(320, 'd');

//Configure the frame trigger and the sequence to the CAN Disturbance Device
if(result == 1)
{
  //Send the sequence immediately on the bus
  result = canDisturbanceTriggerNow(deviceID, sequence);

  if(result == 1)
  {
    result = sequence.ToString(buffer, 1024);
    write("Sequence %s was send with length %d", buffer, result);
    //Output:
    //Sequence ddddddd…ddddd was send with length 320
  }
  else
  {
    write("Error by sequence sending Result =%d", result);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
