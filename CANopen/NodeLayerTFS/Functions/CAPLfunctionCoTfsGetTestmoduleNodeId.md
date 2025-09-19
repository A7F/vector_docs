# coTfsGetTestModuleNodeId

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword coTfsGetTestModuleNodeId( void );
```

## Description

The function gets the node-ID of the tester.

## Parameters

—

## Return Values

Node-ID of the tester.

## Example

```c
dword nodeId;
nodeId = coTfsGetTestModuleNodeId();
```
