# Diagnostics: Access Mode

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE

Parameter access functions can access the transmitted value as follows:

- **0**: numerical: Access to the transmitted numerical value.
- **1**: physical: Access to the value calculated from the transmitted numerical value (is also displayed symbolical as text).
- **2**: coded: Immediate transformation into a numeric type (up to 32 bit), i.e. floating point values will also be provided in their internal description (bit form).

## Example:

Parameter definition in Diagnostic Description:

- Encoding of raw value: 4 Bytes, BCD, Byte Order: LowHigh (Intel)
- Encoding of physical value: 4 Bytes, IEEE Float (single), Precision 2 decimal places
- Formula for physical value: f(x)=(x-20)/50

Parameter bytes in PDU (i.e. in the order of transmission on the bus):

- Raw: 0x03 0x02 0x01 0x00 (i.e. byte sequence [03 02 01 00], can be retrieved e.g. by using `DiagGetParameterRaw`)

Parameter values depending on access mode:

- Numerical: 10203.0 (value of BCD-encoded byte sequence [00 01 02 03], inverse order of bytes compared to raw due to Intel format).
- Physical: 203.66 (formula applied to numerical value, (10203-20)/50=203.66).
- Coded: 66051.0 (decimal value of byte sequence [00 01 02 03] interpreted as 4 byte integer).

[diagGetComplexParameter](Functions/CAPLfunctionDiagGetComplexParameter.md) • [diagGetComplexRespParameter](Functions/CAPLfunctionDiagGetComplexRespParameter.md) • [diagGetParameter](Functions/CAPLfunctionDiagGetParameter.md) • [diagGetRespParameter](Functions/CAPLfunctionDiagGetRespParameter.md) • [diagSetComplexParameter](Functions/CAPLfunctionDiagSetComplexParameter.md) • [diagSetParameter](Functions/CAPLfunctionDiagSetParameter.md)
