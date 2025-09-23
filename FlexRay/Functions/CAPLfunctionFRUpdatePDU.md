[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRUpdatePDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frUpdatePDU

# frUpdatePDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
When the appropriate Tx buffers are declared by the Tx buffer list of the hardware configuration dialog, then the function [frSetSendPDU](CAPLfunctionFRSetSendPDU.md) in `on preStart` is deprecated.  
Is the update time close to the sending slot (e.g. update of slot 2 just after the start of a cycle), then with high probability the update will be too late for the current cycle and the frame is sent in the next possible cycle! Thus, updates should be made early enough before the sending slot of the PDU.

## Function Syntax

```plaintext
void frUpdatePDU(<PDU var>, dword flags, int updateCounter);
```

## Description

This function updates the PDU payload in the assigned FlexRay frames.  
The update bit can also be set.

## Parameters

- **`<PDU var>`**  
  Name of the variable referenced by the PDU object.  
  The variable name was defined via [frPDU](../Objects/CAPLfunctionFrPDU.md) when the object was created.

- **flags**  
  - **Bitmask**  
    - `0x01`: Update bit is set on transmission.  
    - All other bits are reserved and must be set to a value of 0.

- **updateCounter**  
  - **Value**  
    - `-1`: The PDU is transmitted in every configured slot.  
    - `0`: The PDU's default value is transmitted.  
    - `N (>0)`: The PDU is transmitted at least n times.

## Return Values

—

## Example

The following example assumes that the database defines a PDU that is named **PDU_CNT_02** and that this PDU contains a signal that is named **counter**.  
This program sends the PDU once every 64 cycles. The update is made on the beginning of cycle 0.

```plaintext
variables
{
    frPDU MsgChannel%CHANNEL%.PDU_CNT_02 gPDU1;
    BYTE gCycle; // remember current FlexRay cycle
}
on preStart
{
    // Optionally prepare buffer for PDU gPDU1:
    frSetSendPDU(gPDU1);
}
on frStartCycle 0
{
    if (this.MsgChannel != %CHANNEL%) return;
    gCycle = this.FR_Cycle;
    gPDU1.counter = gCycle;
    frUpdatePDU(gPDU1, 1, 1); // set update bit and send only once
}
```
