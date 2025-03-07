[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionA664MsgConfig.md)

**CAPL Functions** » [AFDX](../CAPLfunctionsAFDXOverview.md) » A664MsgConfig

# A664MsgConfig

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

1. `long A664MsgConfig (a664Frame aFrame, dword IpFrag, dword Line, dword SubVlId)`
2. `long A664MsgConfig (a664Message aMessage, dword IpFrag, dword Line, dword SubVlId)`

## Description

Configure the Tx parameters for a given a664Frame or a664Message.

**Note**

- Some parameters may vary for different messages on the same VL like 'LineSelect' or 'IpFragAllowd'. In this case the `<A664VLConfig>`-function defines the default setting within this VL; for dedicated messages those parameters can be overwritten using `<A664MessageConfig>`.
- If the message is defined in the database, there is no need to explicitly call this function, because the DBC-values are used as initial default; but you can overwrite those settings by use of this function.
- For any of the input parameters a value of `0xffffffff` respective "A664_IGNORE_PARAM" can be used to use the currently set control parameter further on. This allows defining only a subset, leaving the other parameters unchanged.

## Parameters

- **IpFrag** (this parameter is ignored for a664Frame):
  - 0 no IP fragmentation
  - 1 message may be fragmented

- **Line** (with this parameter the line settings of the VL may be overwritten for this a664Frame or a664Message)

  **Line definition:**

  - **0**: Line assignment is derived from the VL settings (selector LineSelect)
  - **1**: ForceA - Use line A
  - **2**: ForceB - Use line B
  - **3**: ForceAB - Use both lines

- **SubVlId**: Specify the SubVLid, used for this message or frame. The allowed value range is 1 .. 4. The value is not checked against the selector SubVLNr.

## Return Values

- **0**: No error.
- **2**: SubVLId out of range.
- **3**: Line not available.

## Example

```plaintext
  a664Message DEMOMSG_ALLTYPES myMsg = {msgChannel = 1};
  myMsg.TxCycle = 100;  // overwrite DBC-send period for this message
  a664VLConfig(myMsg, 3, 4, 8, 1024, 65000); // special BAG and maxFrameSize
  a664MsgConfig(myMsg, 0, 3, 2);  // overwrite doFrag and SubVL
  a664TriggerMessage(myMsg, 2);  // start cyclic transmission
```

[See Also](javascript:void(0);)