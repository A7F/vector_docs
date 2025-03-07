[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionADASActivateFMU.md)

[CAPL Functions](../../CAPLfunctions.md) » [ADAS](../CAPLfunctionsADASOverview.md) » ADASActivateFMU

# ADASActivateFMU

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long ADASActivateFMU( char fmuName[], long activationState );
```

## Description

This method is used to activate or deactivate additional ADAS processing steps to allow communication with a [FMU](../../../CANoeCANalyzer/Interfaces/FMIConfig.md) with the specified name. It is assumed that the FMU has been coupled with your CANoe DE product via the [FMI](../../../CANoeCANalyzer/Interfaces/FMI.md). Please note that the specified FMU needs to serve [specific input and output interfaces](../../../CANoeCANalyzer/ADAS/Interfaces/ADASFMU.md) for this function to have any effects. If no FMU with that name was found, the internal processing steps and thus this function call will also have no effects.

## Parameters

- **fmuName**: The name of the FMU
- **activationState**: Specifies whether additional ADAS processing steps for the specified FMU should be activated (1) or deactivated (0)

## Return Values

- **0**: Success, the additional ADAS processing steps were successfully activated/deactivated
- **1**: Invalid value for activationState (must be 0 or 1)

## Example

```plaintext
on key ‘a’
{
  ADASActivateFMU("MyFMU", 1); // Activate FMU
}
on key ‘d’
{
  ADASActivateFMU("MyFMU", 0); // Deactivate FMU
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)