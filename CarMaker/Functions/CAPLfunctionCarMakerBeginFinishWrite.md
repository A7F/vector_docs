# CarMaker_BeginWrite, CarMaker_FinishWrite

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long CarMaker_BeginWrite( );
long CarMaker_FinishWrite( );
```

## Description

Groups several write operations to a single atomic write operation. All write operations succeeding `CarMaker_BeginWrite` are buffered until the call to `CarMaker_FinishWrite`.

## Parameters

—

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
CarMaker_BeginWrite();
CarMaker_WriteAbs("DM.UserSignal_0", 500, 1.0);
CarMaker_WriteAbs("DM.UserSignal_1", 500, -0.3);
CarMaker_FinishWrite();
```
