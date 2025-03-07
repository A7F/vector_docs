[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTParamGet.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostParamGet

# mostParamGet

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
double mostParamGet (mostAmsMessage msg, char paramAdr[]); // form 1
double mostParamGet (mostAmsMessage msg, char paramAdr[], long arrayIndex); // form 2
```

## Description

Query of a parameter value from an AMS message using the parameter name from the XML function catalog.

Suitable for parameter types 'Number', 'Enum', 'BitField' and 'Bool'.

**Note:** For parameters of type 'Array' or 'Sequence' the size (number of elements) of the parameter is retrieved. The array size cannot be determined, if the parameter 'Pos' selects only one array element.

**Example:** 
```plaintext
mostAmsMessage AudioDiskPlayer.MediaInfo.Status msg;
int arraySize;
mostParamSet(msg, "Pos", 0x0200); // second array element selected
arraySize = mostParamGet(msg, "Data"); // Return value '0'
```

**Note:** The message data must contain a parameter with the given parameter address. Since the compiler is not able to validate this, errors are detected at runtime of the CAPL program only. If the parameter is not part of the message or not the expected type, an error text is displayed in the Write Window and the measurement stops. The function [mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) can be applied to assure parameter availability.

## Parameters

- **msg**: Message from which the parameter value should be read.
- **paramAdr**: Identification of parameters (see [symbolic identification of parameters](../CAPLfunctionsMOSTSymIDParam.md)).
- **arrayIndex**: Parameter index in arrays or sequences. This declaration overwrites the indexing in the brackets of `<paramAdr>`.

## Return Values

Raw value of the parameter. No conversion formula is applied.

## Example

—

[mostParamIsAvailable](CAPLfunctionMOSTParamIsAvailable.md) • [mostParamGetData](CAPLfunctionMOSTParamGetData.md) • [mostParamGetString](CAPLfunctionMOSTParamGetString.md) • [mostParamSet](CAPLfunctionMOSTParamSet.md) • [mostParamSetData](CAPLfunctionMOSTParamSetData.md) • [mostParamSetString](CAPLfunctionMOSTParamSetString.md) • [General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md) • [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)