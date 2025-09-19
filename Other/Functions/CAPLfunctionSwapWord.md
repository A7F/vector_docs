[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSwapWord.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » swapWord, swapInt, swapDWord, swapLong, swapInt64, swapQWord

# swapWord, swapInt, swapDWord, swapLong, swapInt64, swapQWord

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `word swapWord(word x); // form 1`
- `int swapInt(int x); // form 2`
- `dword swapDWord(dword x); // form 3`
- `long swapLong(long x); // form 4`
- `int64 swapInt64(int64 x); // form 5`
- `qword swapQWord(qword x); // form 6`

## Description

Swaps bytes of parameters. CAPL arithmetics follows the "little-endian-format" (Intel). The swap-functions serve for swapping bytes for the transition to and from the "big-endian-format" (Motorola).

## Parameters

Value whose bytes are to be swapped.

## Return Values

Value with swapped bytes.

## Example

```plaintext
bigEndian = swapInt(1234); // create constant 1234 for Motorola processors
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
