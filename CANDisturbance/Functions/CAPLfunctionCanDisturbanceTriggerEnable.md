# canDisturbanceTriggerEnable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long canDisturbanceTriggerEnable(long deviceID, canDisturbanceFrameTrigger trigger, canDisturbanceSequence sequence); // form 1
long canDisturbanceTriggerEnable(long deviceID, canDisturbanceFrameTrigger trigger, canDisturbanceSequence sequence, canDisturbanceTriggerRepetitions repetitions); // form 2
long canDisturbanceTriggerEnable(long deviceID, canDisturbanceFrameTrigger trigger, canDisturbanceSequence sequence, canDisturbanceTriggerRepetitions repetitions, dword flags); // form 3
```

## Description

Configures a frame trigger and a user-defined output sequence on a CAN Disturbance Interface. When the trigger condition is fulfilled, the CAN Disturbance Interface starts sending the given sequence on the bus. The starting point of the sequence can be configured by the **canDisturbanceFrameTrigger** parameter. A typical use case for this function is to send a sequence within a CAN frame, to disturb a single bit or a range of bits.

### Constraints

If the level of the trigger bit must be a specific level (dominant or recessive), the value of the bit is measured at the sample point. If the margin sync time (MST) between sample point and the start of the next bit is smaller than the delay time (DT) that is needed to send the sequence on the bus, the sequence is not synchronized to the start of the next bit.

## Parameters

- **deviceID**: The unique device ID that is configured via the [Network Hardware Configuration](../../../CANoeCANalyzer/Ribbon/Hardware/NetworkHardware/NetworkHardwareCAN.md) dialog for a CAN channel.
- **trigger**: The frame trigger condition for the CAN Disturbance Interface to output the sequence.
- **sequence**: The user-defined sequence that is sent if the trigger condition is fulfilled.
- **repetitions**: The trigger repetitions. If the trigger repetitions are not defined, the CAN Disturbance Interface uses default values.
- **flags**: The flags can be used to set a digital input line as an additional trigger enable for the trigger condition. If the flags are not defined, the default value 0x0 is used.

  Possible values:

  - **0x0**: Disabled - No digital input (DIN) is used as trigger enable for the trigger condition.
  - **0x1**: DIN0 Active_Low - If DIN0 is 0, the trigger is enabled
  - **0x2**: DIN0 Active_High - If DIN0 is 1, the trigger is enabled
  - **0x4**: DIN1 Active_Low - If DIN1 is 0, the trigger is enabled
  - **0x8**: DIN1 Active_High - If DIN1 is 1, the trigger is enabled
  - **0x10**: [Inverted Trigger](../../../CANoeCANalyzer/Interfaces/CANDisturbance/ConfigTrigger.md#InvertedTrigger)
    - 0: Inverted trigger is disabled
    - 1: Inverted trigger is enabled
  - **0x20**: Rx Direction*
    - 0: Direction trigger is disabled
    - 1: Direction trigger is enabled
  - **0x40**: [Tx Direction](../../../CANoeCANalyzer/Interfaces/CANDisturbance/ConfigTrigger.md#SendDirectionTrigger)*
    - 0: Direction trigger is disabled
    - 1: Direction trigger is enabled
  - **0x80**: [Missing Bit Trigger](../../../CANoeCANalyzer/Interfaces/CANDisturbance/ConfigTrigger.md#MissingBitTrigger) - Trigger also, trigger position is not included within frame.

  It is only possible to use either **DIN0** or **DIN1** as trigger enable. If both are configured, the function returns an error. If a trigger enable is configured, an external trigger cannot be configured. Inverted, Rx, Tx and bit missing trigger can be configured together with a trigger enable trigger. *The direction trigger has only be set if a specific direction should only be disturbed. If nothing is set both Tx and Rx frames are triggering a configured trigger.

## Return Values

- **1**: Success
- **0**: Error
- **-1**: Device ID was not assigned to CAN Disturbance Interface
- **-2**: Erroneous trigger definition
- **-3**: Erroneous repetition definition
- **-4**: Erroneous trigger enabling flag combination
- **-5**: Erroneous frame based sequence

## Example

### Example for form 1

```plaintext
CanDisturbanceFrameTrigger frameTrigger;
CanDisturbanceSequence sequence;
long result;
long valditiyMask;
message 0x100 triggerMessage;
long validityMask;

//clear the sequence
sequence.Clear();

//configure the message should be triggered

//ID must standard ID and a CAN message must on the bus
validityMask = @sysvar::CanDisturbance::Enums::ValidityMaskFlags::IDBase
               | @sysvar::CanDisturbance::Enums::ValidityMaskFlags::IDE
               | @sysvar::CanDisturbance::Enums::ValidityMaskFlags::FDF ;

frameTrigger.SetMessage(triggerMessage, deviceID, validityMask);
//trigger position is the CRC delimiter
frameTrigger.TriggerFieldType =
               @sysvar::CanDisturbance::Enums::FieldType::CRCDel;
frameTrigger.TriggerFieldOffset = 0;

//configure a sequence 320 FPGA ticks long and send a recessive bit at the Ack slot bit on the bus. A FPGA tick is 6.25 ns long, which leads to a bit time of 2 µs
result = sequence.AppendToSequence(320, 'R');

//Configure the frame trigger and the sequence to the CAN Disturbance Interface
if(result == 1)
{
  result = canDisturbanceTriggerEnable(deviceID, frameTrigger, sequence);
  if(result == 1)
  {
    write("Trigger is enabled");
  }
  else
  {
    write("Enable trigger error Result =%d", result);
  }
}
```

### Example for form 2

```plaintext
CanDisturbanceFrameTrigger frameTrigger;
CanDisturbanceSequence sequence;
CanDisturbanceTriggerRepetitions repetitions;
long result;
long validityMask;
message 0x100x triggerMessage;

//clear the sequence
sequence.Clear();

//configure the message should be triggered

//ID must extended ID and a CAN message must on the bus
validityMask = @sysvar::CanDisturbance::Enums::ValidityMaskFlags::IDBase
               | @sysvar::CanDisturbance::Enums::ValidityMaskFlags::IDExtended
               | @sysvar::CanDisturbance::Enums::ValidityMaskFlags::IDE
               | @sysvar::CanDisturbance::Enums::ValidityMaskFlags::FDF;

frameTrigger.SetMessage(triggerMessage, deviceID, validityMask);
//trigger position is the ACK Slot
frameTrigger.TriggerFieldType =
               @sysvar::CanDisturbance::Enums::FieldType::ACKSlot;
frameTrigger.TriggerFieldOffset = 0;

// configure a sequence 320 FPGA ticks long and send a dominant bit at the Ack Delimiter bit on the bus. A FPGA tick is 6.25 ns long, which leads to a bit time of 2 µs
result = sequence.AppendToSequence(320, 'd');

//Define two repetitions and one cycle with a 1 ms hold off time
repetitions.Cycles = 1;
repetitions.HoldOffCycles = 1;
repetitions.HoldOffRepetitions = 0;
repetitions.Repetitions = 33;

//Configure the frame trigger and the sequence to the CAN Disturbance Interface
if(result == 1)
{
  result = canDisturbanceTriggerEnable(deviceID, frameTrigger, sequence,
  repetitions);
  if(result == 1)
  {
    write("Trigger is enabled");
  }
  else
  {
    write("Enable trigger error Result =%d", result);
  }
}
```

### Example for form 3

```plaintext
CanDisturbanceFrameTrigger frameTrigger;
CanDisturbanceSequence sequence;
CanDisturbanceTriggerRepetitions repetitions;
long result;
long validityMask;
message 0x100x triggerMessage;
dword flags;

//clear the sequence
sequence.Clear();
//configure the message should be triggered

//ID must extended ID and a CAN message must on the bus
validityMask = @sysvar::CanDisturbance::Enums::ValidityMaskFlags::IDBase
               | @sysvar::CanDisturbance::Enums::ValidityMaskFlags::IDExtended
               | @sysvar::CanDisturbance::Enums::ValidityMaskFlags::IDE
               | @sysvar::CanDisturbance::Enums::ValidityMaskFlags::FDF;

frameTrigger.SetMessage(triggerMessage, deviceID, validityMask);
//trigger position is the ACK Slot
frameTrigger.TriggerFieldType =
               @sysvar::CanDisturbance::Enums::FieldType::ACKSlot;
frameTrigger.TriggerFieldOffset = 0;

//configure a sequence 320 FPGA ticks long and send a dominant bit at the Ack Delimiter bit on the bus. A FPGA tick is 6.25 ns long, which leads to a bit time of 2 µs
result = sequence.AppendToSequence(320, 'd');

//Define 33 repetitions and one cycle with a 1 ms hold off time
repetitions.Cycles = 1;
repetitions.HoldOffCycles = 1;
repetitions.HoldOffRepetitions = 0;
repetitions.Repetitions = 33;

//define trigger enable, if DIO0 is active high the trigger could be trigger
flags = @sysvar::CanDisturbance::Enums::TriggerEnable::DIN0ActiveHigh;

//Configure the frame trigger and the sequence to the CAN Disturbance Interface
if(result == 1)
{
  result = canDisturbanceTriggerEnable(deviceID, frameTrigger,
  sequence, repetitions, flags);
  if(result == 1)
  {
    write("Trigger is enabled");
  }
  else
  {
    write("Enable trigger error Result =%d", result);
  }
}
```
