[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerWriteAbs.md)

**CAPL Functions** » **CarMaker Interface** » **CarMaker_WriteAbs**

# CarMaker_WriteAbs

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CarMaker_WriteAbs(char varName[], double duration_ms, double value);
```

## Description

Modifies the value of a CarMaker quantity. The CarMaker quantity must support write access.

## Parameters

- **varName**: Absolute name of the CarMaker quantity.
- **duration_ms**: Duration for fixing the value.
- **value**: The new value to be set.

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
gErrorState = CarMaker_WriteAbs("DM.Brake", 1000, 1.0);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)