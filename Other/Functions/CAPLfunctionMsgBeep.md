[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionMsgBeep.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » msgBeep

# msgBeep

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note:** If the specified sound type (e.g. MB_ICONHAND) cannot be played, the standard beep (computer speaker) is used. The beep must be activated on the Windows panel to do this!

## Function Syntax

```plaintext
void msgBeep (long soundType);
```

## Description

The `msgBeep` function plays back a sound predefined by the Windows system. It replaces the previous beep function.

## Parameters

- **soundType**: Integer for the predefined sound. Specifically these are:
  - `0`: MB_ICONASTERISK SystemAsterisk
  - `1`: MB_ICONEXCLAMATION SystemExclamation
  - `2`: MB_ICONHAND SystemHand
  - `3`: MB_ICONQUESTION SystemQuestion
  - `4`: MB_OK SystemDefault
  - `5`: Standard beep using the computer speaker (default)

## Return Values

—

## Example

```c
void sound() {
// Standard signal question
msgBeep (3);
}
```

[write](CAPLfunctionWrite.md) • [writeToLog](CAPLfunctionWriteToLog.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
