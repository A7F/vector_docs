# Iso11783PDDObjectPoolDeactivate

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDObjectPoolDeactivate( dword ecuHandle );
```

## Description

The function sends an Object-pool Deactivate message to the Task Controller and disconnects the connection to the Task Controller.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md) beforehand or ZERO for general parameters.

## Return Values

[Error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
if (Iso11783PDDObjectPoolDeactivate(ecuHandle) == 0) {
  write("Node has disconnected from the Task Controller");
}
```
