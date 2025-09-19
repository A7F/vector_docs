# C2xStopNode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xStopNode(); //form 1`
- `long C2xStopNode(char* nodeName); //form 2`

## Description

The function stops the transmission of messages for a specified node.

## Parameters

- **nodeName**: Name of the node that stops the transmission.

## Return Values

- **1**: —
- **≠1**: Error code

## Example

```c
//form 1
C2xStopNode();
//form 2
C2xStopNode("Node1");
```

[C2xStartNode](CAPLfunctionC2xStartNode.md)
