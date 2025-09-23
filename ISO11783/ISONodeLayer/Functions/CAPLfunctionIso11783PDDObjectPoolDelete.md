# Iso11783PDDObjectPoolDelete

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDObjectPoolDelete( dword ecuHandle );
```

## Description

The function deletes the current device description object pool and sends an Object-pool Delete message to the Task Controller.

Contrary to [Iso11783PDDDelete](CAPLfunctionIso11783PDDdelete.md) the connection to the Task Controller is not removed.

## Parameters

- **ecuHandle**:
  - Handle of the ECU.
  - The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md) beforehand or ZERO for general parameters.

## Return Values

[Error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
if (Iso11783PDDObjectPoolDelete( ecuHandle ) == 0) {
  write("Object pool is deleted and Object-Pool delete message is sent successfully");
}
```
