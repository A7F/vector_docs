# _Diag_SendFunctional

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
void _Diag_SendFunctional (BYTE data[]);
```

## Description

With this CAPL callback function CANoe triggers the CAPL program to send a functional diagnostic request.

## Parameters

- **data**: The data of the diagnostic primitive (request) that should be transmitted on the bus.

## Return Values

—

## Example

```plaintext
_Diag_SendFunctional( BYTE data[])
{
  // Send data on the functional TP connection created earlier
  CanTpSendData( gHandleFunctional, data, elcount( data));
  write("_Diag_SendFunctional data[0]=%d", data[0]);
}
```
