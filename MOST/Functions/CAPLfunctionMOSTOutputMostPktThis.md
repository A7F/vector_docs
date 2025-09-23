[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTOutputMostPktThis.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » outputMostPktThis

# outputMostPktThis

**Valid for**: CANoe DE

**Note**: `outputMostPktThis()` may only be called within the [OnMostPkt()](../EventProcedures/CAPLfunctionOnMOSTPkt.md) event procedure.

## Function Syntax

`outputMostPktThis();`

## Description

Passes the packet on to the next node in the nodal sequence.

## Parameters

—

## Return Values

—

## Example

Packet filter in CAPL:

```plaintext
OnMostPkt(long pktdatalen)
{
   // filter destination address 0x100
   if(mostPktDestAdr() == 0x100)
   {
      // forward packet to the successor
      outputMostPktThis(); 
   }
}
```

[output](CAPLfunctionMOSToutput.md) • [outputMostPkt](CAPLfunctionMOSTOutputMostPkt.md)
