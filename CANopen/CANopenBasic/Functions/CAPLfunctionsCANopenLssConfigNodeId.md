# CANopenLssConfigNodeId

**Valid for**: [CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword CANopenLssConfigNodeId (byte nodeId);
```

## Description

The LSS master configures the node ID of a LSS slave.

## Parameters

- **nodeId**: New node ID of the LSS slave.

## Return Values

- **0**: Successful
- **1**: Invalid channel (not CAN or inactive)
- **2**: Invalid node ID

## Example

```c
//Assignes node ID 7 to the current LSS slave
CANopenLssConfigNodeId(7);
```
