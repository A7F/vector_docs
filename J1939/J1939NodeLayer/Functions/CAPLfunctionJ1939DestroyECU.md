# J1939DestroyECU

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939DestroyECU( dword ecuHandle );
```

## Description

This function deletes a logical node that was generated with [J1939CreateECU()](CAPLfunctionJ1939CreateECU.md) from the network.

**Important Note**

You should avoid allowing this function to be called within a CAPL callback function, since otherwise data consistency of the node layer could be violated.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```
J1939DestroyECU(ecuHandle);
```
