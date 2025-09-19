[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStartMacroFile.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » StartMacroFile

# StartMacroFile

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
Note that a relative path to the configuration directory or an absolute path can be specified for the macro file. Just the filename of the macro can also be specified. For this option, the macro file must be located in the same folder as the configuration.

## Function Syntax

```
dword StartMacroFile(char fileName[]);
```

## Description

Starts playing the macro with the **fileName** filename.

## Parameters

- **fileName**: Macro file.

## Return Values

The returned handle is required to [stop the macro playback](CAPLfunctionStopMacroFile.md).

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
