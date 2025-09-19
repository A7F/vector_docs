[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeFontAttr.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPChangeFontAttribute

# Iso11783IL_OPChangeFontAttribute

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPChangeFontAttribute( dword objectID, dword color, dword size, dword type, dword style ); // form 1
long Iso11783IL_OPChangeFontAttribute( dbNode implement, dword objectID, dword color, dword size, dword type, dword style ); // form 2
```

## Description

The function changes the properties of a font attribute object. A **Change Font Attribute** command is sent to the Virtual Terminal.

## Parameters

- **objectID**: Object ID of the font attribute object
- **color**: Color index
- **size**: Size of the font:
  - 0: 6x8
  - 1: 8x8
  - 2: 8x12
  - 3: 12x16
  - 4: 16x16
  - 5: 16x24
  - 6: 24x32
  - 7: 32x32
  - 8: 32x48
  - 9: 48x64
  - 10: 64x64
  - 11: 64x96
  - 12: 96x128
  - 13: 128x128
  - 14: 128x192
- **type**: Font type:
  - 0: ISO8859-1 (ISO Latin 1)
  - 1: ISO8859-15 (ISO Latin 9)
  - 2: ISO8859-2 (ISO Latin 2)
- **style**: Font style:
  - Bit 0: 1 Bold
  - Bit 1: 1 Crossed out
  - Bit 2: 1 Underlined
  - Bit 3: 1 Italic
  - Bit 4: 1 Inverted
  - Bit 5: 1 Flashing
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeFontAttribute( 1100, 10, 3, 0, 0x01 );
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
