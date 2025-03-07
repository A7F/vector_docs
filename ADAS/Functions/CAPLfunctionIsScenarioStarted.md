[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADAS/Functions/CAPLfunctionIsScenarioStarted.md)

**CAPL Functions** » **ADAS** » **IsScenarioStarted**

# IsScenarioStarted

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This CAPL function is also available as C# function.

## Function Syntax

**C#**  
`bool IsScenarioStarted.Call();`

**CAPL**  
`int IsScenarioStarted.Call();`

## Description

Queries whether the currently loaded scenario has started.

## Parameters

—

## Return Values

**C#**

- **true**: Scenario is started
- **false**: Scenario is not started

**CAPL**

- **1**: Scenario is started
- **0**: Scenario is not started

## Example

In the examples it is assumed in each case that a DO object of the type IScenarioManager was created.

### CAPL

```capl
int result = ScenarioManager.IsScenarioStarted.Call();
```

### C#

```csharp
bool result = ScenarioManager.IsScenarioStarted.Call();
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)