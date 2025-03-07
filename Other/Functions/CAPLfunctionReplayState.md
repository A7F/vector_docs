[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionReplayState.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » ReplayState

# ReplayState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword ReplayState (char pName[]);
```

## Description

Returns the state of the Replay Block with the name **pName**.

## Parameters

- **pName**: Name of the Replay Block

## Return Values

- **0**: Replay Block is stopped (state: stopped)
- **1**: Execution of the Replay file was started (state: running)
- **2**: Execution of the Replay file was stopped (state: suspended)
- **(dword)-1**: when the Replay Block does not exist

## Example

See [ReplayState](CAPLfunctionsExampleReplay.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)