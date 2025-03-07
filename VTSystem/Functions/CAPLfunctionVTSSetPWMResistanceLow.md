[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetPWMResistanceLow.md)

**CAPL Functions** » **VT System** » **SetPWMResistanceLow**

# SetPWMResistanceLow

**Valid for:** CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of channels belonging to the **VT System** module **VT2004**.

## Method Syntax

`long SysVarNamespace.SetPWMResistanceLow (double Resistance);`

## Description

Specifies the resistance value of a low signal on PWM output in **Resistance output PWM** mode.

## Parameters

- **Resistance**  
  Resistance value in ohms.  
  Resistance may have values from 1.0 (1 Ω) up to 250000.0 (250 kΩ). This range is only supported by channel **4** of the **VT2004** module. The other channels can handle values from 10.0 (10 Ω) up to 150000.0 (150 kΩ).  
  In special cases Resistance may be set to **-1** on each channel to get infinite resistance.  
  Values outside the hardware's possible range of values are rounded up to the next highest value or the highest or lowest possible value is used.

## Return Values

- **0**  
  Successful call
- **-1**  
  Call error
- **-2**  
  The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.
- **-3**  
  The specified resistance is not valid
- **-4**  
  The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the **VT System**. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

See example [SetPWMResistanceHigh](CAPLfunctionVTSSetPWMResistanceHigh.md)

[vtsSetPWMResistanceLow](CAPLfunctionVTSvtsSetPWMResistanceLow.md)

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)