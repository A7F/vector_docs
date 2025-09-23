# J1939GetWSMaster

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939GetWSMaster

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939GetWSMaster(char busName[], dword ecuAddress)
```

## Description

This function returns the address of the Working Set Master, which is assigned to an ECU with the address `ecuAddress`.

## Parameters

- **busName**: name of the bus
- **ecuAddress**: address of an ECU

## Return Values

Address of the Working Set Master

## Example

```c
wsmAddr = J1939GetWSMaster("default", 10);
```
