[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MATLAB/CAPLfunctionsMATLABOverview.md)

[CAPL Functions](../CAPLfunctions.md) » MATLAB Integration CAPL Functions

# MATLAB Integration CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**MATLAB**  
Only available with MATLAB Integration Package.

The Simulink Coder generated DLL contains three additional functions which can be called by CAPL. These functions may be used to control the behavior of the generated CANoe MATLAB Integration and the execution of the Simulink model.

**Note**  
The CANoe MATLAB Integration uses meaningful default values to set up and control Simulink model execution. These defaults are determined during the generation process by the Simulink Coder. If you use the CAPL functions described herein you can override these defaults and take control of model execution.

**Note to Function Notation**  
**`<ModelName>`** = placeholder for Simulink model

## Export CAPL Functions

- The CAPL functions described herein are only exported if this option is **on**. Default value is **off**.
- Long model filenames (> 44 characters) are only supported if this option is **off**.

| Functions | Short Description |
|-----------|-------------------|
| [`<ModelName>`_init](Functions/CAPLfunctionMODELinit.md) | Initializes the CANoe runtime environment for the generated model DLL. |
| [`<ModelName>`_step](Functions/CAPLfunctionMODELstep.md) | Executes a simulation step. |
| [GetSimulinkModelName](Functions/CAPLfunctionGetSimulinkModelName.md) | Returns the name of the Simulink model. |

## CAPL Functions in Concurrent Execution Mode

If the model was built as **Concurrent Execution 64 Bit Real-Time DLL**, the CAPL function `<ModelName>_step` does not perform the whole simulation step, it just triggers its execution on a separate thread. When the simulation step is completed, the DLL calls the CAPL function `void on_<ModelName>_step_completed()` if this function was implemented by the user. For an example, see the sample configuration [Concurrent Execution with External CAPL Scheduler](../../SampConf/Matlab/MATLABConcurrentExecutionCAPLScheduler.md).

[MATLAB Integration](../../CANoeCANalyzer/Interfaces/MATLAB/MATLAB.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
