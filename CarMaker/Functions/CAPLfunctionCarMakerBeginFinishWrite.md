[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerBeginFinishWrite.md)

**CAPL Functions** » **CarMaker Interface** » **CarMaker_BeginWrite, CarMaker_FinishWrite**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)