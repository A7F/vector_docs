# canDisturbanceTriggerNow

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

- `long canDisturbanceTriggerNow(long deviceID, canDisturbanceSequence); // form 1`
- `long canDisturbanceTriggerNow(long deviceID, canDisturbanceSequence, canDisturbanceTriggerRepetitions repetitions);// form 2`
- `long canDisturbanceTriggerNow(long deviceID, canDisturbanceFrameSequence sequence); // form 3`
- `long canDisturbanceTriggerNow(long deviceID, canDisturbanceFrameSequence sequence, canDisturbanceTriggerRepetitions repetitions); // form 4`

## Description

Sends a user-defined sequence or a frame-based sequence on the bus with the CAN Disturbance Interface. The sequence or frame-based sequence sends directly on the bus. If a frame is currently sent by another interface, this frame will be disturbed. A typical use case is to send a sequence or a frame based sequence on the bus without any trigger conditions.

## Parameters

- **deviceID**: The unique device ID configured via the [Network Hardware Configuration](../../../CANoeCANalyzer/Ribbon/Hardware/NetworkHardware/NetworkHardwareCAN.md) dialog for a CAN channel.
- **sequence**: The user-defined sequence or frame based sequence.
- **repetitions**: The repetitions of the output sequence.

## Return Values

- **1**: Success
- **0**: Error
- **-1**: Device ID was not assigned to CAN Disturbance Interface
- **-3**: Repetition definition with errors
- **-5**: Frame based sequence with sequence errors
- **-7**: Sequence definition with errors

## Example

**Example for form 1**

```plaintext
CanDisturbanceSequence   sequence;
long                     result;

//Clear sequence
sequence.Clear();

//configure a sequence one bit long and send a dominant bit
result = sequence.AppendToSequence(320, 'd');

if(result == 1)
{
  result= canDisturbanceTriggerNow(deviceID, sequence);

  if(result == 1)
  {
    write("Trigger now is configured.");
  }
  else
  {
    write("Error by configuration of trigger now %d", result);
  }
}
```

**Example for form 2**

```plaintext
CanDisturbanceSequence               sequence;
CanDisturbanceTriggerRepetitions     repetitions;
long                                 result;

//Clear sequence
sequence.Clear();

//configure a sequence one bit long and send a dominant bit
result = sequence.AppendToSequence(320, 'd');

if(result == 1)
{
  //Define two repetitions and one cycle with a 1 ms hold off time
  repetitions.Cycles = 1;
  repetitions.HoldOffCycles = 1;
  repetitions.HoldOffRepetitions = 1;
  repetitions.Repetitions = 2;

  result= canDisturbanceTriggerNow(deviceID, sequence, repetitions);

  if(result == 1)
  {
    write("Trigger now is configured.");
  }
  else
  {
    write("Error by configuration of trigger now %d", result);
  }
}
```

**Example for form 3**

```plaintext
canDisturbanceFrameSequence   frameSequence;
message 0x100                 msgFrameSeq;
long                          result;

//set message to sequence
frameSequence.SetMessage(deviceID, msgFrameSeq);
result = canDisturbanceTriggerNow(deviceID, frameSequence);

if(result == 1)
{
  write("Trigger now is configured.");
}
else
{
  write("Error by configuration of trigger now %d", result);
}
```

**Example for form 4**

```plaintext
canDisturbanceFrameSequence             frameSequence;
canDisturbanceTriggerRepetitions        repetitions;
message 0x100                           msgFrameSeq;
long                                    result;

//set message to sequence
frameSequence.SetMessage(deviceID, msgFrameSeq);

//Define two repetitions and one cycle with a 1 ms hold off time
repetitions.Cycles = 1;
repetitions.HoldOffCycles = 1;
repetitions.HoldOffRepetitions = 1;
repetitions.Repetitions = 2;

//output the sequence twice
result = canDisturbanceTriggerNow(deviceID, frameSequence, repetitions);

if(result == 1)
{
  write("Trigger now is configured.");
}
else
{
  write("Error by configuration of trigger now %d", result);
}
```
