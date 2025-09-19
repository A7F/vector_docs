[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MATLAB/Functions/CAPLfunctionMODELstep.md)

[CAPL Functions](../../CAPLfunctions.md) » [MATLAB Integration](../CAPLfunctionsMATLABOverview.md) » `<ModelName>_step`

# `<ModelName>_step`

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
`<ModelName>` = placeholder for Simulink model

## Function Syntax

```plaintext
long <ModelName>_step();
```

## Description

Executes a simulation step.

## Parameters

—

## Return Values

On success 0, otherwise a value unequal to zero.

## Example

```plaintext
on timer modelTimer
{
    myControllerMdl_step();
}
```

[See Also](javascript:void(0);)
```markdown
<ModelName>_init  
GetSimulinkModelName  
MATLAB Integration CAPL Functions
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)