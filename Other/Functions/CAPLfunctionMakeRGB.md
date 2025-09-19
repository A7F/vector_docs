[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMakeRGB.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » MakeRGB

# MakeRGB

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MakeRGB(long Red, long Green, long Blue);
```

## Description

Calculates the color value from the three primary color components.

The value is interpreted as 4 bytes and the color results from which value is contained in which byte:

[0] = ignored, [1] = **Red**, [2] = **Green**, [3] = **Blue**

See also [availability for panel controls](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/General/PanelDesignerCAPLFunctions.md)

## Parameters

- **Red**: Red color component (0 - 255)
- **Green**: Green color component (0 - 255)
- **Blue**: Blue color component (0 - 255)

## Return Values

- **Color value (type long)**

## Example

```plaintext
MakeRGB(255, 128, 0); // orange color
```

[MakeARGB](CAPLfunctionMakeARGB.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
