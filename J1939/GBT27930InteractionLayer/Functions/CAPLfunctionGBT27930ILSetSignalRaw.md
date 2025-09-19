[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILSetSignalRaw.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_SetSignalRaw

# GBT27930IL_SetSignalRaw

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_SetSignalRaw(dbSignal signal, long value ); // form 1
long GBT27930IL_SetSignalRaw(dbNode node, dbSignal signal, long value ); // form 2
```

## Description

Sets the signal to the specified raw value. The message of the signal is sent according to the configured send type.

## Parameters

- **signal**: signal name from database  
  The signal must be assigned to the node as [Tx signal](../../../../CANoeCANalyzer/J1939/j1939IL/j1939ILConfigureDB.md).

- **value**: raw value

- **node**: Simulation node to apply the function

## Return Values

- **0**: success

- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 't'
{
    GBT27930IL_SetSignalRaw( EEC1::EngSpeed, 12000 );
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
