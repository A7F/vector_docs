[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTParamSet.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostParamSet

# mostParamSet

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostParamSet(mostAmsMessage msg, char paramAdr[], double value); // form 1
long mostParamSet(mostAmsMessage msg, char paramAdr[], long arrayIndex, double value); // form 2
```

## Description

Setting of a parameter value in an AMS message using the parameter name from the XML function catalog.

Suitable for parameter types 'Number', 'Enum', 'BitField' and 'Bool'.

For parameters of the 'Enum' type, the numeric value can be specified. The [mostParamSetString](CAPLfunctionMOSTParamSetString.md) function can be used to set the symbolic value.

**Note**: For arrays and sequences the size (number of elements) of the parameter is set. The array size cannot be set, if the parameter 'Pos' selects only one array element.

**Example**:

```plaintext
mostAmsMessage AudioDiskPlayer.MediaInfo.Status msg;
mostParamSet(msg, "Pos", 0x0200); // second array element selected
mostParamSet(msg, "Data", 6); // Returns an error code at runtime! Array size can only be set if Pos selects all array elements.
```

**Note**: The message data must contain a parameter with the given parameter address. Since the compiler is not able to validate this, errors are detected at runtime of the CAPL program only. If the parameter is not part of the message or not the expected type, an error text is displayed in the Write Window and the measurement stops. The function [mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) can be applied to assure parameter availability.

When using function mostParamSet to build a message dump, the parameters must be populated in the order specified by the MOST Function Catalog, particularly for messages with StreamCases.

## Parameters

- **msg**: Message in which the parameter value should be described.
- **paramAdr**: Identification of parameters (see [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)).
- **arrayIndex**: Parameter index in arrays or sequences. This declaration overwrites the indexing in the brackets of `<paramAdr>`.
- **value**: Value of the parameter with whole-number parameter types, decimal places are truncated. A raw value is expected i.e. no conversion formula is applied.

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) • [mostParamGet](CAPLfunctionMOSTParamGet.md) • [mostParamGetData](CAPLfunctionMOSTParamGetData.md) • [mostParamGetString](CAPLfunctionMOSTParamGetString.md) • [mostParamSetData](CAPLfunctionMOSTParamSetData.md) • [mostParamSetString](CAPLfunctionMOSTParamSetString.md) • [General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md) • [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)