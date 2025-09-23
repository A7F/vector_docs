[J1939AppCmdAddrIndication](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939AppCmdAddrIndication.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939AppCmdAddrIndication

# J1939AppCmdAddrIndication (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939AppCmdAddrIndication( long ecuHandle, long length );
```

## Description

This function indicates that a new address has been assigned to the control device by the "CommandedAddress". The ECU must log on to the bus with the assigned address (see [J1939ECUGoOnline()](CAPLfunctionJ1939ECUGoOnline.md)).

Since the PG also returns the name of the ECU, the data must be requested within this callback with [J1939GetRxData()](CAPLfunctionJ1939GetRxData.md). This function is only called if the ECU can change its address (‘Self Configuring Address’-Bit of the device name must be set).

## Parameters

- **ecuHandle**: ECU handle
- **length**: number of received data bytes

## Return Values

—

## Example

```plaintext
dword J1939AppCmdAddrIndication( LONG ecuHandle, LONG length)
{
    /* user code */
}
```
