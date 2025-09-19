# C2xStartNode

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long C2xStartNode(); //form 1
long C2xStartNode(char* nodeName); //form 2
```

## Description

## Parameters

- **nodeName**: Name of the node that starts the transmission

## Return Values

- **1**: —
- **≠1**: Error code

## Example

```plaintext
//form 1
C2xStartNode();
//form 2
C2xStartNode("Node1");
```

[C2xStopNode](CAPLfunctionC2xStopNode.md)
