# on frFrameError

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/EventProcedures/CAPLfunctionOnFRFrameError.md)

**CAPL Functions** » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » on frFrameError

## Function Syntax

- `on frFrameError *;` // form 1

This procedure is always called whenever the frame definitions below do NOT occur. In other words, for a specific frame, only this function or the formats below will be called!

- `on frFrameError <frame name>;` // form 2

Uses a symbolic frame name from the database.

- `on frFrameError (<slot ID>, <base cycle>, <cycle repetition>);` // form 3

This function is only called for an erroneous frame in a specific slot.

This event procedure is called after a frame has been received in slot `<slot ID>` and a cycle corresponding to the Cycle Multiplexing has been received erroneously. Potential frames are received from the `<z>` cycles that conform to the following formula:  
`<z> modulo <cycle repetition> = <base cycle>`

## Description

The event procedure is called if an erroneous frame is received in the specified slot and cycle.

If two erroneous frames are received in the corresponding slot (on channel A and on B), then the event procedure is called twice (once for each frame).

An optional channel parameter for event filtering can be assigned to all handlers:

**Example I**  
In this example, the event procedure is only called for erroneous frames whose application channel is 2 and its ID is 5.

`on frFrameError MsgChannel2.(5,0,1)`

An optional qualifier can be used to assign the handler to a specific network:

**Example II**  
In this example, the event procedure is only called for erroneous frames from the application channel that is named "network" in the Simulation Setup.

`on frFrameError network.<frame name>`

## Parameters

- `*`: Specifies the default procedure. This procedure is called for all received erroneous frames for which there is no explicit event procedure.

- `<frame name>`: Character string corresponding to a frame name from the database. The required parameters (`<slot ID>`, `<base cycle>` and `<cycle repetition>`) are taken from the corresponding frame definition in the database.

- `<slot ID>`: This number designates a specific slot. Its value must be between 1 and 2047.

- `<base cycle>`: This number designates the base cycle. This value must be smaller than the repetition factor and lie in the range between 0 and 63. This value, together with the repetition factor, determines the **Cycle Multiplexing**.

- `<cycle repetition>`: This number designates the cycle repetition factor. The value must be between 1 and 64 and be a multiple of 2 (e.g. 1, 2, 4, 8, 16, 32 or 64). This value, together with the base cycle, determines the **Cycle Multiplexing**.

## Selectors

The same selectors as for [on frFrame](CAPLfunctionOnFRFrame.md) can be applied.

**All selectors are write-protected!**

## Example

The following program reacts on frame errors and prints them in the Write Window.

```plaintext
variables
{
   const int cWriteTextSize = 512;
   char writeTxt[cWriteTextSize];
}
float getTime (float time)
{
   return time / 1000000000.0;
}
void myprint(char text[])
{
   write("%s", text);
}
on frFrameError *
{
   snprintf(writeTxt, cWriteTextSize, "%10.6f: on FRFrameError in slot %2d in cycle %2d on channel %2d with mask %d with Type %2d, Flags 0x%02x, Status 0x%02x, Simulated %d.", getTime(messageTimeNS(this)), this.FR_SlotID, this.FR_Cycle, (int)this.MsgChannel, this.FR_ChannelMask, this.Type, this.FR_Flags, this.FR_Status, this.Simulated);
   myprint(writeTxt);
   output(this); // only required in Measurement Setup
}
```
