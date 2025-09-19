[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTParamGetString.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostParamGetString

# mostParamGetString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostParamGetString (mostAmsMessage msg, char paramAdr[], char buffer[], long buffersize); // form 1
long mostParamGetString (mostAmsMessage msg, char paramAdr[], long arrayIndex, char buffer[], long buffersize); // form 2
```

## Description

Query of parameters of the String type from an AMS message using the parameter name from the XML function catalog.

**Note**: This function supports ASCII-coded strings only. In case of other string encoding use the function [mostParamGetData](CAPLfunctionMOSTParamGetData.md).

**Note**: The message data must contain a parameter with the given parameter address. Since the compiler is not able to validate this, errors are detected at runtime of the CAPL program only. If the parameter is not part of the message or not the expected type, an error text is displayed in the Write Window and the measurement stops. The function [mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) can be applied to assure parameter availability.

## Parameters

- **msg**: Message from which the parameter should be read.
- **paramAdr**: Identification of parameters (see [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)).
- **arrayIndex**: Parameter index in arrays or sequences. This declaration overwrites the indexing in the brackets of `<paramAdr>`.
- **buffer**: Buffer to which the parameter bytes are copied.
- **buffersize**: Maximum number of copied parameter bytes (can be specified with `(elcount(buffer))`).

## Return Values

- **>=0**: Number of copied bytes.
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) • [mostParamGet](CAPLfunctionMOSTParamGet.md) • [mostParamGetData](CAPLfunctionMOSTParamGetData.md) • [mostParamGetStringAscii](CAPLfunctionMOSTParamGetStringAscii.md) • [mostParamSet](CAPLfunctionMOSTParamSet.md) • [mostParamSetData](CAPLfunctionMOSTParamSetData.md) • [mostParamSetString](CAPLfunctionMOSTParamSetString.md) • [General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md) • [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
