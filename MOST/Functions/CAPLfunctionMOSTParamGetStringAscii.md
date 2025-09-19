[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTParamGetStringAscii.md)

CAPL Function Overview » [MOST](../CAPLfunctionsMOSTOverview.md) » mostParamGetStringAscii

# mostParamGetStringAscii

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostParamGetStringAscii(mostAmsMessage msg, char paramAdr[], char buffer[], long buffersize); // form 1
long mostParamGetStringAscii(mostAmsMessage msg, char paramAdr[], long arrayIndex, char buffer[], long buffersize); // form 2
```

## Description

Query of parameters of the String type from an AMS message and decode to ASCII format using the parameter name from the XML function catalog. Unsupported characters are ignored.

**Note**: The message data must contain a parameter with the given parameter address. Since the compiler is not able to validate this, errors are detected at runtime of the CAPL program only. If the parameter is not part of the message or not the expected type, an error text is displayed in the Write Window and the measurement stops. The function [mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) can be applied to assure parameter availability.

## Parameters

- **msg**: Message in which the parameter value should be described.
- **paramAdr**: Identification of parameters (see [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)).
- **arrayIndex**: Parameter index in arrays or sequences. This declaration overwrites the indexing in the brackets of `<paramAdr>`.
- **buffer**: Buffer to which the ASCII string parameter is copied.
- **bufferSize**: Maximum number of copied ASCII string parameter bytes (can be specified with ([elcount](../../Other/Functions/CAPLfunctionElCount.md)(buffer))).

## Return Values

- **>=0**: number of converted characters
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

```plaintext
on mostAmsMessage AmFmTuner.RadioText.Status
{
  char buffer[200];
  long dataLen;
  // get string parameter data
  datalen = mostParamGetStringAscii(this, "TextA", buffer, elcount(buffer));
  if(datalen >= 0)
  {
    write("Radiotext: %s", buffer);
  }
}
```

Input: Message parameter bytes: 00 00 61 00 62 00 63 00 00  
Output: Radiotext: abc

## Related Links

- [OnMostApInstID](../EventProcedures/CAPLfunctionOnMOSTApInstID.md)
- [mostParamGet](CAPLfunctionMOSTParamGet.md)
- [mostParamGetData](CAPLfunctionMOSTParamGetData.md)
- [mostParamGetString](CAPLfunctionMOSTParamGetString.md)
- [mostParamSet](CAPLfunctionMOSTParamSet.md)
- [mostParamSetData](CAPLfunctionMOSTParamSetData.md)
- [mostParamSetStringEnc](CAPLfunctionMOSTParamSetStringEnc.md)
- [General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md)
- [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
