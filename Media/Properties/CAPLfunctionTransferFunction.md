[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/Properties/CAPLfunctionTransferFunction.md)

CAPL Functions » [Media API](../CAPLfunctionsMediaOverview.md) » [Properties](../CAPLfunctionsMediaProperties.md) » TransferFunction

# TransferFunction

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Property

TransferFunction

## Description

Specifies the conversion function from RGB to R'G'B' for a video media type.

## Data Type

dword

## Remarks

The value of this property is one of the following:

- VideoTransFunc_Unknown = 0,
- VideoTransFunc_10 = 1,
- VideoTransFunc_18 = 2,
- VideoTransFunc_20 = 3,
- VideoTransFunc_22 = 4,
- VideoTransFunc_709 = 5,
- VideoTransFunc_240M = 6,
- VideoTransFunc_sRGB = 7,
- VideoTransFunc_28 = 8,
- VideoTransFunc_Log_100 = 9,
- VideoTransFunc_Log_316 = 10,
- VideoTransFunc_709_sym = 11,
- VideoTransFunc_2020_const = 12,
- VideoTransFunc_2020 = 13,
- VideoTransFunc_26 = 14,
- VideoTransFunc_2084 = 15,
- VideoTransFunc_HLG = 16,
- VideoTransFunc_Last, MFVideoTransFunc_ForceDWORD = 0x7FFFFFFF

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
