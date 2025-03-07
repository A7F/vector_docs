[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTParamSetStringEnc.md)

CAPL Function Overview » [MOST](../CAPLfunctionsMOSTOverview.md) » mostParamSetStringEnc

# mostParamSetStringEnc

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostParamSetStringEnc (mostAmsMessage msg, char paramAdr[], long encoding, char asciiStr[]); // form 1
long mostParamSetStringEnc (mostAmsMessage msg, char paramAdr[], long arrayIndex, long encoding, char asciiStr[]); // form 2
```

## Description

Encoding and setting of parameters of the String type (for ASCII-coded strings only) in an AMS message using the parameter name from the XML function catalog. Only ASCII-coded strings are supported.

**Note**: The parameter description must go with the message content. The compiler is not able to validate this here. Errors only appear at runtime of the CAPL program, if applicable. This function is primarily used to access messages, whose content was previously limited explicitly, e.g. by the declaration. The message must be populated in the order of its parameters particularly for messages with StreamCases. If the parameter is not part of the message or not the expected type, an error message it output in the Write Window and the measurement stops.

## Parameters

- **msg**: Message in which the parameter value should be described.
- **paramAdr**: Identification of parameters (see [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)).
- **arrayIndex**: Parameter index in arrays or sequences. This declaration overwrites the indexing in the brackets of `<paramAdr>`.
- **enconding**: Specifies the target encoding. Supported target encodings:
  - `0x00`: Unicode, UTF16
  - `0x01`: ISO 8859/15 8 bit
  - `0x02`: Unicode, UTF8
  - `0x03`: RDS
  - `0x04`: DAB Charset 0001
  - `0x05`: DAB Charset 0010
  - `0x06`: DAB Charset 0011
  - `0x07`: SHIFT_JIS
- **asciiStr**: String that should be encoded and copied to the message.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

```plaintext
mostAmsMessage AmFmTuner.RadioText.Status msg;
mostParamSetString(msg, "TextA", 0x00, "abc");
```

- -> Message parameter bytes: 00 00 61 00 62 00 63 00 00

## Related Links

- [OnMostApInstID](../EventProcedures/CAPLfunctionOnMOSTApInstID.md)
- [mostParamSetString](CAPLfunctionMOSTParamSetString.md)
- [mostParamGet](CAPLfunctionMOSTParamGet.md)
- [mostParamGetData](CAPLfunctionMOSTParamGetData.md)
- [mostParamGetString](CAPLfunctionMOSTParamGetString.md)
- [mostParamSet](CAPLfunctionMOSTParamSet.md)
- [mostParamSetData](CAPLfunctionMOSTParamSetData.md)
- [mostParamGetStringAscii](CAPLfunctionMOSTParamGetStringAscii.md)
- [General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md)
- [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)