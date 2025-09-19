[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionHalt.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » halt

# halt

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void halt();
```

## Description

The function stops both the debugged program as well as the simulation. The debugger window opens and the halt() command is displayed. The function thus creates a breakpoint while simultaneously interrupting the measurement in simulated mode (also for test modules). The simulation can be continued with `<F9>`. For usage in Real Mode, it is only activated for test modules and test configurations otherwise the halt instruction is ignored.

## Parameters

—

## Return Values

—

## Example

```plaintext
on key 'h'
{
  halt(); 
  // Stops execution of the simulation in Simulation mode
}
```

[Debugging](../../../CANoeCANalyzer/Debugger/DebuggerDebugging.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
