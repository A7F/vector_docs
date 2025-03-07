[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTParamSetString.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostParamSetString

# mostParamSetString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostParamSetString (mostAmsMessage msg, char paramAdr[], char value[]); // form 1`
- `long mostParamSetString (mostAmsMessage msg, char paramAdr[], long arrayIndex, char value[]); // form 2`

## Description

Setting of parameters of the String type (for ASCII-coded strings only) or of the 'Enum' type in an AMS message using the parameter name from the XML function catalog.

**Note**: This function supports ASCII-coded strings only. In case of other string encoding use the function [mostParamSetData](CAPLfunctionMOSTParamSetData.md). For enumerations, the parameter value can be indicated symbolically. The [mostParamSet](CAPLfunctionMOSTParamSet.md) function can be used to set the numeric value.

**Note**: The message data must contain a parameter with the given parameter address. Since the compiler is not able to validate this, errors are detected at runtime of the CAPL program only. If the parameter is not part of the message or not the expected type, an error text is displayed in the Write Window and the measurement stops. The function [mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) can be applied to assure parameter availability. When using function mostParamSetString to build a message dump, the parameters must be populated in the order specified by the MOST Function Catalog, particularly for messages with StreamCases.

## Parameters

- **msg**: Message in which the parameter value should be described.
- **paramAdr**: Identification of parameters (see [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)).
- **arrayIndex**: Parameter index in arrays or sequences. This declaration overwrites the indexing in the brackets of `<paramAdr>`.
- **value**: String: Characters that should be copied to the message. Enumeration: Symbolic name of the parameter value.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[OnMostApInstID](../EventProcedures/CAPLfunctionOnMOSTApInstID.md) • [mostParamSetStringEnc](CAPLfunctionMOSTParamSetStringEnc.md) • [mostParamGet](CAPLfunctionMOSTParamGet.md) • [mostParamGetData](CAPLfunctionMOSTParamGetData.md) • [mostParamGetString](CAPLfunctionMOSTParamGetString.md) • [mostParamSet](CAPLfunctionMOSTParamSet.md) • [mostParamSetData](CAPLfunctionMOSTParamSetData.md) • [General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md) • [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)