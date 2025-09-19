# A664VLConfig

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long A664VLConfig (a664Frame aFrame, dword RxFlags, dword TxFlags, dword BagValue, dword MaxFrameSize, dword SkewMax) (1)
```

```
long A664VLConfig (a664Message aMessage, dword RxFlags, dword TxFlags, dword BagValue, dword MaxFrameSize, dword SkewMax) (2)
```

## Description

Configure a Virtual-Link for a given a664Frame or a664Message.

**Note**

- Some parameters may vary for different messages on the same VL like **LineSelect** or **IpFragAllowed**. In this case, the function **A664VLConfig** defines the default setting within this VL. For dedicated messages, those parameters can be overwritten using **A664MessageConfig**.
- If the message is defined in the database, there is no need to explicitly call this function, because the DBC-values are used as initial default. However, you can overwrite those settings by using this function.
- For any of the input parameters, a value of `0xffffffff` respective "A664_IGNORE_PARAM" can be used to use the currently set control parameter further on. This allows defining only a subset, leaving the other parameters unchanged.

## Parameters

- **RxFlags**: Control integrity checking (IntChk: bit position 0) and redundancy management (RMA: bit position 1).
- **IntChk**
  - 0 set integrity checking to OFF
  - 1 set integrity checking to ON
- **RMA**
  - 0 set redundancy management to OFF
  - 1 set redundancy management to ON
- **TxFlags**: Control the selected line (LineSelect: bit position 0, 1) and IP fragmentation (IpFragAllowed: bit position 2).
- **LineSelect**
  - 0 use existing value from LineSelect for transmission
  - 1 transmit on line A
  - 2 transmit on line B
  - 3 transmit on both lines
- **IpFragAllowed**
  - 0 fragmentation not allowed
  - 1 fragments are allowed
- **BagValue**: Give the BAG for this VL.
- **MaxFrameSize**: Give the maximum Ethernet packet size MaxFrameSize for this VL.
- **SkewMax**: This is the maximum timely difference between a transmission on line A and B. The value SkewMax is considered for Rx direction only.

## Return Values

- **0**: No error
- **1**: BAG value out of range.
- **2**: SkewMax out of range.
- **3**: Frame size out of range.

## Example

See [A664MsgConfig](CAPLfunctionA664MsgConfig.md).
