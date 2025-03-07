[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetOutputRange.md)

**CAPL Functions** » **VT System** » **SetOutputRange**

# SetOutputRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**: The function can only be called on system variable namespaces of appropriate channels of **VT System** modules.

## Method Syntax

```plaintext
long SysVarNamespace.SetOutputRange (eVTSOutputRange Range);
```

## Description

Sets the range that is used for analog output on output channels of **VT2816** modules.

## Parameters

- **Range**: Values see [eVTSOutputRange](../CAPLfunctionsVTSystemEnumeration.md#eVTSOutputRange)

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**: The specified mode is not valid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the **VT System**. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

```plaintext
sysvar::VTS::TempSensor.SetOutputRange (eVTSOutputRangePlusMinus10V);
```

[vtsSetOutputRange](CAPLfunctionVTSvtsSetOutputRange.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)