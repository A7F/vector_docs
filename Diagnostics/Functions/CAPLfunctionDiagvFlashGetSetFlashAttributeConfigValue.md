[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagvFlashGetSetFlashAttributeConfigValue.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » vFlashGetFlashAttributeConfigValue, vFlashGetFlashAttributeLastRunValue, vFlashSetFlashAttribute

# vFlashGetFlashAttributeConfigValue, vFlashGetFlashAttributeLastRunValue, vFlashSetFlashAttribute

Valid for: CANoe DE

**Note**  
With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.  
See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

- `long vFlashGetFlashAttributeConfigValue(char flashAttributeName[], char valueOut[], dword maxLen); // form 1`
- `long vFlashGetFlashAttributeLastRunValue(char flashAttributeName[], char valueOut[], dword maxLen); // form 2`
- `long vFlashSetFlashAttribute(char flashAttributeName[], char attributeValue[]); // form 3`

## Description

Get the value of a Flash attribute, either as configured in the vFlash project (form 1), or the value set by the flash procedure the last time the flash project was executed (form 2). It is also possible to set the value of the Flash attribute (form 3) used for next execution (not persistently in project).

## Parameters

- **flashAttributeName**: Name of the attribute as shown in vFlash.
- **valueOut**: Buffer for returning the value of the attribute.
- **maxLen**: Length of the buffer provided.
- **attributeValue**: New value of the attribute, as text. Note that it must be possible to convert the text into the type defined for the attribute. For example, integer attributes accept only values in the form `1234` or `0xABC`, otherwise an error is returned.

## Return Values

- **1**: Success
- **1055**: Attribute cannot be found
- **1056**: Attribute value could not be converted (e.g. string cannot be converted into an integer)
- **other**: error code; refer to (Reusable) vFlash/Utilities.cin for a list of error and status codes

## Example

```c
char valueOut[200];
char attributeName[30] = "Flash Attribute";

// Read the value configured in the project
vFlashGetFlashAttributeConfigValue(attributeName, valueOut, elcount(valueOut));

// Set the value to use the next time
vFlashSetFlashAttribute(attributeName, "1234");

// perform flashing
TestWaitForvFlashReprogrammed();

// Retrieve the value the flash procedure might have set during the last run
vFlashGetFlashAttributeLastRunValue(attributeName, valueOut, elcount(valueOut));
```

[vFlashGetCustomActionAttributeConfigValue, vFlashGetCustomActionAttributeLastRunValue, vFlashSetCustomActionAttribute](CAPLfunctionDiagvFlashGetGetSetCustomActionAttribute.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)