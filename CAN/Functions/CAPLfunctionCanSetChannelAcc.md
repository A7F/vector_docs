[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionCanSetChannelAcc.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » canSetChannelAcc

# canSetChannelAcc

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

**Note**  
This function can only be used with Vector drivers. The `vcndrvms.DLL` must be at least Version 4.2.40.

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

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)