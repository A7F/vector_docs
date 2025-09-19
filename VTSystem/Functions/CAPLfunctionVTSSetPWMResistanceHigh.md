[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetPWMResistanceHigh.md)

**CAPL Functions** » **VT System** » **SetPWMResistanceHigh**

# SetPWMResistanceHigh

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of channels belonging to the **VT System** module **VT2004**.

## Method Syntax

`long SysVarNamespace.SetPWMResistanceHigh (double Resistance);`

## Description

Specifies the resistance value of a high signal on PWM output in "Resistance output PWM" mode.

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

The following example demonstrates how to use the internal resistor decade of a **VT2004** channel to simulate a PWM based sensor. On channel **Temp_Sensor** the resistor is toggled between 100 Ohm and 140 Ohm with a frequency of 20 Hz and a duty cycle of 50%.

### CAPL

```capl
SimulateSensorPWMResistance ()
{
   // Choose resistor stimulation and a PWM curve type
   sysvar::VTS::Temp_Sensor.SetStimulationMode(3);
   sysvar::VTS::Temp_Sensor.SetCurveType(1);

   // Configure low (100Ohm) and high (140Ohm) resistance values
   sysvar::VTS::Temp_Sensor.SetPWMResistanceLow(100);
   sysvar::VTS::Temp_Sensor.SetPWMResistanceHigh(140);

   // Set the number of repeats to unlimited
   sysvar::VTS::Temp_Sensor.SetPWMRepeats(0);

   // Create a PWM signal with frequency 20Hz and DC 50%
   @sysvar::VTS::Temp_Sensor::PWMFreq = 20.0;
   @sysvar::VTS::Temp_Sensor::PWMDC = 50.0;

   // Start the stimulation
   sysvar::VTS::Temp_Sensor.StartStimulation();
}
```

### .NET (C#)

```csharp
public void SimulateSensorPWMResistance()
{
    // Get VTS interface and VT2004 channel
    IVTSystem vts = VTSystem.Instance;
    IVT2004Channel tempSensor = vts.GetChannel("Temp_Sensor") as IVT2004Channel;

    // Choose resistor stimulation and a PWM curve type
    tempSensor.SetStimulationMode(StimulationMode.ResistanceLower, CurveType.PWM);

    // Configure low (100Ohm) and high (140Ohm) resistance values
    tempSensor.PWMResistanceLow.Value = 100.0;
    tempSensor.PWMResistanceHigh.Value = 140.0;

    // Set the number of repeats to unlimited
    tempSensor.PWMRepeats.Value = 0;

    // Start the stimulation
    tempSensor.StartStimulation();

    // Create a PWM signal with frequency 20Hz and DC 50%
    tempSensor.PWMFreq.Value = 20.0;
    tempSensor.PWMDC.Value = 50.0;
}
```

### [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md)

[vtsSetPWMResistanceHigh](CAPLfunctionVTSvtsSetPWMResistanceHigh.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
