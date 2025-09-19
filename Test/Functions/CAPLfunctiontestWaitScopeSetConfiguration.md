[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctiontestWaitScopeSetConfiguration.md)

**CAPL Functions** » **Scope** » **testWaitScopeSetConfiguration**

# testWaitScopeSetConfiguration

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testWaitScopeSetConfiguration (char deviceName[], char configurationName[]);
```

## Description

Configures the appropriate oscilloscope with the specified configuration.

Hint: The possible device names and configurations names can be requested with the function [testWaitScopeGetConfigurationInformation](CAPLfunctionTestWaitScopeGetConfigurationInformation.md).

## Parameters

- **deviceName**: The name of the scope device.
- **configurationNames**: The specific configuration should be used for the scope device.

## Return Values

- **1**: Successful
- **0**: Timeout
- **-20**: The current configuration could not be changed.
- **-21**: The device name is not available.
- **-22**: A configuration with the specified name could not be found.
- **-23**: The specified configuration is invalid and cannot be set.

## Example

```c
void SetScopeConfiguration()
{
    long res;

    res = testWaitScopeSetConfiguration("Scope_1", "MyConfiguration");

    if (res != 1)
    {
        testStepFail("SetConfiguration","Set configuration MyConfiguration of Scope_1 was not possible. Result = %d", res);
    }
    else
    {
        testStepPass("SetConfiguration", "Configuration of Scope_1 is set to MyConfiguration");
    }
}
```

See also: [testWaitScopeGetConfigurationInformation](CAPLfunctionTestWaitScopeGetConfigurationInformation.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
