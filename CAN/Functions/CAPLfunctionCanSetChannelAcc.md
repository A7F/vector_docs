# canSetChannelAcc

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

**Note**  

## Function Syntax

`long canSetChannelAcc(long channel, dword code, dword mask);`

## Description

Via an acceptance filter, the CAN controllers control which received messages are sent through to your CANoe DE product. Some controller chips, such as the SJA 1000, expect partitioning into acceptance mask and acceptance code.

## Parameters

- **channel**: CAN channel
- **code**: Acceptance code
- **mask**: Acceptance mask

## Return Values

- **0**: ok
- **!=0**: error

## Example

```plaintext
on key 'a'
{
    /*
    To distinguish whether the filter is for standard or extended identifier. For extended identifiers the MSB of the code and mask are set.
    Description:
    Different ports may have different filters for a channel. If the CAN hardware cannot implement the filter, the driver virtualises filtering.
    Accept if ((id ^ code) & mask) == 0).
    */
    long channel = 2;
    dword code = 0x10;
    dword mask = 0x10;
    canSetChannelAcc(channel, code, mask);
    write("channel mask set");
}
```

[canSetChannelMode](CAPLfunctionCanSetChannelMode.md) • [canSetChannelOutput](CAPLfunctionCanSetChannelOutput.md)
