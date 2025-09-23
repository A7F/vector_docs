# J1939ILSetSignal

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILSetSignal(dbSignal signal, double value ); // form 1
long J1939ILSetSignal(dbNode node, dbSignal signal, double value ); // form 2
```

## Description

Sets the signal to the specified physical value. The message of the signal is sent according to the configured send type.

## Parameters

- **signal**: signal name from database. The signal must be assigned to the node as [Tx signal](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILConfigureDB.md).
- **value**: physical value
- **node**: Simulation node to apply the function

## Return Values

- **0**: success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't'
{
    J1939ILSetSignal( EEC1::EngSpeed, 1200.0 );
}
```
