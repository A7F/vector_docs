[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagvFlashGetGetSetCustomActionAttribute.md)

**CAPL Functions** » **Diagnostics** » vFlashGetCustomActionAttributeConfigValue, vFlashGetCustomActionAttributeLastRunValue, vFlashSetCustomActionAttribute

# vFlashGetCustomActionAttributeConfigValue, vFlashGetCustomActionAttributeLastRunValue, vFlashSetCustomActionAttribute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.  
See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

- `long vFlashGetCustomActionAttributeConfigValue(char customActionAttributeName[], char valueOut[], dword maxLen); // form 1`
- `long vFlashGetCustomActionAttributeLastRunValue(char customActionAttributeName[], char valueOut[], dword maxLen); // form 2`
- `long vFlashSetCustomActionAttribute(char customActionAttributeName[], char attributeValue[]); // form 3`

## Description

Get the value of a vFlash CustomAction attribute, either as configured in the vFlash project (form 1), or the value set by the CustomAction script the last time the flash project was executed (form 2). It is also possible to set the value of the CustomAction attribute (form 3) used for next execution (not persistently in project).

## Parameters

- **customActionAttributeName**: Name of the attribute as shown in vFlash.
- **valueOut**: Buffer for returning the value of the attribute.
- **maxLen**: Length of the buffer provided.
- **attributeValue**: New value of the attribute, as text. Note that it must be possible to convert the text into the type defined for the attribute. For example, integer attributes accept only values in the form **1234** or **0xABC**, otherwise an error is returned.

## Return Values

- **1**: Success
- **1055**: Attribute cannot be found
- **2060**: General error executing Custom Action
- **2061**: Value given for the Custom Action Attribute could not be converted (e.g. string cannot be converted into an integer)
- **other**: error code; refer to (Reusable) vFlash/Utilities.cin for a list of error and status codes

## Example

```c
char valueOut[200];
char attributeName[30] = "Custom Action Attribute 1";

// Read the value configured in the project
vFlashGetCustomActionAttributeConfigValue(attributeName, valueOut, elcount(valueOut));

// Set the value to use the next time
vFlashSetCustomActionAttribute(attributeName, "1234");

// perform flashing
TestWaitForvFlashReprogrammed();

// Retrieve the value the custom action script might have set during the last run
vFlashGetCustomActionAttributeLastRunValue(attributeName, valueOut, elcount(valueOut));
```

[vFlashGetFlashAttributeConfigValue, vFlashGetFlashAttributeLastRunValue, vFlashSetFlashAttribute](CAPLfunctionDiagvFlashGetSetFlashAttributeConfigValue.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)