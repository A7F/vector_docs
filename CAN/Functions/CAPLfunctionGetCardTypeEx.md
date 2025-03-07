[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionGetCardTypeEx.md)

**CAPL Functions** » [CAN](../CAPLfunctionsCANOverview.md) » getCardTypeEx

# getCardTypeEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
int getCardTypeEx(int can);
```

## Description

Determines the card type of CAN channel. Is needed e.g. to program the [BTR](CAPLfunctionSetBtr.md) / [OCR](CAPLfunctionSetOcr.md) values.

## Parameters

- **CAN**: Channel number

## Return Values

Type of board as one of the following values:

- **-1**: Unknown or Invalid hardware type
- **3**: DEMO - Demo driver
- **25**: Vector PCMCIA CANcardXL
- **27**: Vector USB CANcaseXL
- **28**: Vector CANcaseXLLog (USB + memory)
- **29**: Vector CANboardXL PCI
- **30**: Vector CPCI CANboardXL Compact
- **31**: Vector CANboardXL PCI express
- **33**: Vector VN7600
- **34**: Vector ExpressCard CANcardXLe
- **36**: Vector VN3300
- **37**: Vector VN3600
- **38**: Vector VN2610
- **40**: Vector VN8950
- **41**: Remote (IP) Device
- **46**: Vector VT6104
- **47**: Vector VN8970
- **48**: Vector VN2640
- **49**: Vector VN1610
- **50**: Vector VN1611
- **51**: Vector VN1630
- **52**: Vector VN1640
- **53**: Vector VN5610
- **54**: Vector VN7570
- **55**: Vector IP Server
- **56**: Vector VT6204
- **61**: Vector VN7572
- **62**: Vector VN8972
- **63**: Vector VN7610
- **71**: Vector VN5640
- **75**: Vector VX1131
- **76**: Vector VN5610A

Additional types may be added!

## Example

—

[getChipType](CAPLfunctionGetChipType.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)