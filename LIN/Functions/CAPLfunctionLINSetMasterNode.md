[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetMasterNode.md)

# linSetMasterNode

[CAPL Functions](../../CAPLfunctions.md) » LIN » linSetMasterNode

**Valid for**: CANoe DE

## Function Syntax

- `long linSetMasterNode(); // form 1`
- `long linSetMasterNode(long nodeId); // form 2`
- `long linSetMasterNode(char nodeNameOrTitle[]); // form 3`

## Description

Changes the LIN master node of the channel given by the current node’s bus context and restricts sending LIN headers solely to the assigned master node. See [SetBusContext](../../Other/Functions/CAPLfunctionSetBusContext.md) for how to change the current bus context.

LIN Header’s can now be sent:

- using the function [linTransmitHeader](CAPLfunctionLINTransmitHeader.md),
- using output(linFrame) with linFrame.RTR=1 (legacy functions)
- using a node layer DLL

The restriction can later be repealed by calling [linResetMasterNode](CAPLfunctionLINResetMasterNode.md).

Using this function allows to include alternative implementations of a LIN master in a CANoe Simulation Setup, and switch between them during measurement. Only the currently assigned LIN master node will be able to output LIN headers. Header transmitted by other (non-master) nodes will be suppressed.

If a node assigned to the LDF master has no longer the master role, the LIN scheduler defined in the LDF will be automatically stopped. If the LDF master node is reassigned by calling [linSetMasterNode](#), the LIN scheduler will be restored to its previous state.

The first prototype of this function assigns the calling simulation node as the LIN master. The value returned is an internal, unique identifier for the previous master node, which can be specified as argument to the second form.

The third prototype specifies a node by its title string (which can be changed in the node configuration). A Replay Block can be assigned to Master mode by its name. The currently assigned master node can be identified by observing the node descriptions in the Simulation Setup window.

## Parameters

- **nodeId**: This parameter specifies a node identifier, which has been returned by an earlier call to [linSetMasterNode](#).

- **nodeNameOrTitle**: The database name (if assigned) or title string of a node.

## Return Values

Node ID of the previous master node. If the return value is 0 (zero), the function failed, or there was no previous LIN master node.

## Example

```plaintext
Variables {
  long prevMasterNode = 0;
}

on key '1': {
  // sets the node executing this CAPL snippet as master
  prevMasterNode = linSetMasterNode();
}

on key '2': {
  // sets the named replay block as master
  prevMasterNode = linSetMasterNode("Replay1");
}

on key '3': {
  // change back to the previous master node
  linSetMasterNode(prevMasterNode);
}
```
