[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTParamIsAvailable.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostParamIsAvailable

# mostParamIsAvailable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostParamIsAvailable(mostAmsMessage * msg, char paramadr[]); // form 1`
- `long mostParamIsAvailable(mostAmsMessage * msg, char paramadr[], long arrayIndex); // form 2`

## Description

Check whether a described parameter with the parameter name from the XML function catalog is in an AMS message.

PosDescription, TelLen and StreamCases are checked in addition to FBlockID, FunctionID and OpType.

This function can be used to prevent erroneous access to messages that can be first identified at runtime of a CAPL program.

## Parameters

- **msg**: Message to which parameter access should be applied.
- **paramAdr**: Identification of parameters (see [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)).
- **arrayIndex**: Parameter index in arrays or sequences. This declaration overwrites the indexing in the brackets of `<paramAdr>`.

## Return Values

- **1**: Parameter is available
- **0**: Parameter is not available

## Example

Assure access to a parameter

In the following sample, access to a parameter is assured in a received message. If the status message is partially transmitted, either through targeted use of the Pos parameter or erroneous assignment of TelLen, it can happen that StartTrack is not part of the received message.

```plaintext
On mostAmsMessage DiskPlayer.MediaInfo.Status
{
    int firstTrack;
    // check whether message was transmitted including FirstTrack of third array element (third media here)
    if(mostParamIsAvailable(this, "Data.Record[].FirstTrack", 3))
    {
        // read FirstTrack from message
        firstTrack = mostParamGet(this, "Data.Record[].FirstTrack", 3);
    }
    else
    {
        // do error handling, either 
        // a) Pos did not indicate existence of FirstTrack (only subset transmitted)
        // b) TelLen was not sufficient (erroneous message transmission)
        // c) Message is no MediaInfo (would only be applicable if ‘On mostAmsMessage’ handler
        //    were not so specific as in this example, error in implementation of model)
        // d) Parameter description was erroneous (error in implementation of model)
        // (Hint: Check if an appropriate XML Function Catalog is assigned to the configuration)
    }
}
```

[mostParamGet](CAPLfunctionMOSTParamGet.md) • [mostParamGetData](CAPLfunctionMOSTParamGetData.md) • [mostParamGetString](CAPLfunctionMOSTParamGetString.md) • [mostParamSet](CAPLfunctionMOSTParamSet.md) • [mostParamSetString](CAPLfunctionMOSTParamSetString.md) • [General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md) • [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)
