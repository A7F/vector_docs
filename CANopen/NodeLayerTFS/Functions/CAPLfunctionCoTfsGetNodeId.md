# coTfsGetNodeId

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword coTfsGetNodeId( void );
```

## Description

This function returns the internally-stored node-ID that is used for the simplified test functions.

## Parameters

—

## Return Values

Node-ID

## Example

```c
dword nodeID;
nodeID = coTfsGetNodeId();
```
