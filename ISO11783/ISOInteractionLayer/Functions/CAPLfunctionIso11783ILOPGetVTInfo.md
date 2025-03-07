[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPGetVTInfo.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_OPGetVTInfo**

# Iso11783IL_OPGetVTInfo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPGetVTInfo( char key[] ); // form 1
long Iso11783IL_OPGetVTInfo( dbNode implement, char key[] ); // form 2
```

## Description

During initialization phase the Object Pool API request some information about the capabilities from Virtual Terminal. These information can be get with this function.

## Parameters

- **key**: Key of information:
  - **"VersionNumber"**: Supported VT version.
  - **"NavigationSoftKeyCount"**: The number of Physical Soft Keys that are used by the VT for navigation among the Virtual Soft Keys.
  - **"SoftKeyWidth"**: Number of pixels on the x-axis for a Soft Key descriptor.
  - **"SoftKeyHeight"**: Number of pixels on the y-axis for a Soft Key descriptor.
  - **"VirtualSoftKeyCount"**: Number of possible virtual Soft Keys in a Soft Key Mask.
  - **"PhysicalSoftKeyCount"**: Number of Physical Soft Keys.
  - **"SmallFontSizes"**: Supported small font sizes.
  - **"LargeFontSizes"**: Supported large font sizes.
  - **"FontTypeAttribute"**: Supported font styles.
  - **"BootTime"**: Maximum number of seconds from a VT power startup.
  - **"GraphicType"**: Supported graphic modes.
  - **"Hardware"**: Supported hardware features.
  - **"Width"**: Number of divisions on the horizontal axis in the Data Mask Area.
  - **"Height"**: Number of divisions on the vertical axis in the Data Mask Area.

- **implement**: Simulation node to apply the function.

## Return Values

- **≥ 0**: Value
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
LONG vtWidth;
vtWidth = Iso11783IL_OPGetVTInfo( "Width" );
```

© Vector Informatik GmbH  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)