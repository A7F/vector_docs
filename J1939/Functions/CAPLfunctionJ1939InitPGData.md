[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/Functions/CAPLfunctionJ1939InitPGData.md)

**CAPL Functions** » [J1939](../CAPLfunctionsJ1939StartPage.md) » [Function Overview](../CAPLfunctionsJ1939Overview.md) » J1939InitPGData

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
