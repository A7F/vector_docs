# J1939InitPGData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939InitPGData (pg * aPG);
```

## Description

Sets all data bytes of the parameter group to 255.

## Parameters

- **aPG**: Parameter group which is initialized.

## Return Values

- **0**: Initialization succeeded
- **-1**: General error

## Example

```c
void SendPositiveAcknowledgment(byte groupFctValue, byte addressAcknowldged, byte pgn)
{
  pg ACKM ackm;
  J1939InitPGData(ackm);
  ackm.sa = 0;
  ackm.da = 1;
  ackm.ControlByte = ACKM.ControlByte::ACK;
  ackm.GroupFunctionValue = groupFctValue;
  ackm.AddressAcknowledged = addressAcknowldged;
  ackm.ParameterGroupNumber = pgn;
  output(ackm);
}
```
