# Iso11783OPGetState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPGetState( dword ecuHandle );
```

## Description

Returns the state of the Object Pool API.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).

## Return Values

- **0**: Not active
- **1**: Wait until ECU is online
- **2**: Wait for status message from VT
- **3**: Initialization phase with the VT
- **4**: Object Pool Upload active or Load Version active
- **5**: Active
- **< 0**: an error has occurred, see [error codes](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
state = Iso11783OPGetState( handle );
```
