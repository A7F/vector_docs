# J1939GetAddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939GetAddress (dbNode aNode);
```

## Description

Gets the current address of a J1939 node even if the address has been changed by the J1939 network management.

## Parameters

- **aNode**: The function returns the address of this node.

## Return Values

- **≥ 0**: Current address of the node.
- **-1**: General error, for example, node does not exist in database.

## Example

```c
dword address;
address = J1939GetAddress (N1);
Write("Address of node N1 is = %i", address );
```
