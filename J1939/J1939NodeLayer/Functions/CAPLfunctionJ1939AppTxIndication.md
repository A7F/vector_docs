[J1939AppTxIndication](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939AppTxIndication.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939AppTxIndication

# J1939AppTxIndication (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939AppTxIndication( long ecuHandle, long txPG, long source, long dest );
```

## Description

Indicates that a PG has been sent successfully. The function for determining the actual sending time can be useful, especially in the case of a fragmented transfer or higher busload. Use the function [J1939GetRxData()](CAPLfunctionJ1939GetRxData.md) to get the data bytes of the parameter group.

## Parameters

- **ecuHandle**: ECU handle
- **txPG**: PGN of the sent parameter group
- **source**: source address
- **destination**: destination address

## Return Values

—

## Example

```plaintext
dword J1939AppTxIndication( LONG ecuHdl, LONG txPG, LONG source, LONG dest )
{
  char data[50];
  J1939GetRxData( elCount(data), data );
  /* user code */
  return 0;
}
```
