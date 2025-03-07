[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMakeARGB.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » MakeARGB

# MakeARGB

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long MakeARGB(long Alpha, long Red, long Green, long Blue);
```

## Description

Calculates the color value from the alpha value and the three primary color components.

The value is interpreted as 4 bytes and the color results from which value is contained in which byte:

[0] = Alpha (transparency), [1] = Red, [2] = Green, [3] = Blue

See also [availability for panel controls](../../../../../Subsystems/VectorToolsEnvironment/Content/Topics/PanelDesigner/General/PanelDesignerCAPLFunctions.md)

## Parameters

- **Alpha**: The transparency of the color (0 - 255)
  - 0: 0% opacity of the color, totally transparent
  - 255: 100% opacity of the color

- **Red**: Red color component (0 - 255)

- **Green**: Green color component (0 - 255)

- **Blue**: Blue color component (0 - 255)

## Return Values

- **Color value (type long)**

## Example

```plaintext
MakeARGB(64, 255, 128, 0); // 25% opacity of orange color
```

[MakeRGB](CAPLfunctionMakeRGB.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)