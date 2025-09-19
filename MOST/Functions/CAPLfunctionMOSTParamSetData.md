[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTParamSetData.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostParamSetData

# mostParamSetData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostParamSetData(mostAmsMessage msg, char paramadr[], byte data[], long datalen); // form 1
long mostParamSetData(mostAmsMessage msg, char paramadr[], long arrayIndex, byte data[], long datalen); // form 2
```

## Description

Setting of parameters of the String type or RawStream in an AMS message using the parameter name from the XML function catalog.

When writing a string parameter with mostParamSetData 'data' has to include the coding byte and terminator character ([mostParamSetString](CAPLfunctionMOSTParamSetString.md) can be used for ASCII coding).

**Note**

The message data must contain a parameter with the given parameter address. Since the compiler is not able to validate this, errors are detected at runtime of the CAPL program only. If the parameter is not part of the message or not the expected type, an error text is displayed in the Write Window and the measurement stops. The function [mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) can be applied to assure parameter availability.

When using function mostParamSetData to build a message dump, the parameters must be populated in the order specified by the MOST Function Catalog, particularly for messages with StreamCases.

## Parameters

- **msg**: Message in which the parameter bytes should be written.
- **paramAdr**: Identification of parameters (see [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)).
- **arrayIndex**: Parameter index in arrays or sequences. This declaration overwrites the indexing in the brackets of `<paramAdr>`.
- **data**: Data from which the parameter bytes are copied.
- **datalen**: Number of valid parameter bytes that are copied to the message.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) • [mostParamGet](CAPLfunctionMOSTParamGet.md) • [mostParamGetData](CAPLfunctionMOSTParamGetData.md) • [mostParamGetString](CAPLfunctionMOSTParamGetString.md) • [mostParamSet](CAPLfunctionMOSTParamSet.md) • [mostParamSetString](CAPLfunctionMOSTParamSetString.md) • [General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md) • [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
