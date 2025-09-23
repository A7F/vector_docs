[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAmsOutput.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAmsOutput

# mostAmsOutput

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `mostAmsOutput(long channel, long destAdr, char symbolicMessage[], long instId); // form 1`
- `mostAmsOutput(long channel, char symbolicMessage[], long instId); // form 2`
- `mostAmsOutput(long channel, char symbolicMessage[]); // form 3`

## Description

Definition and direct dispatch of an AMS message using the syntax from the MOST specification and the description in the XML function catalog.

The description of the message must be complete, i.e., wildcards cannot be used because the message should then be sent directly. However, the parameter list may be shorter than specified in the function catalog, in order to be able to generate intentionally incomplete messages.

## Parameters

- **channel**: Channel of the connected interface.
- **destAdr**: Destination address.
- **symbolicMessage**: Description of the message content in the following formats:
  - `FBlock.InstanceId.Function.OpType(Parameterlist)`
  - `FBlock.InstanceId.Function.OpType`
  - `FBlock.Function.OpType(Parameterlist)`
  - `FBlock.Function.OpType`
- **InstId**: InstanceID of the function block. This explicit entry overwrites the applicable InstanceID in symbolicMessage. If neither an instance ID nor the `instId` parameter is specified in `symbolicMessage`, the default is set to 1.

## Return Values

—

## Example

```c
// send 'play' command for DiskPlayer on MOST ring
on key 'p'
{
   // Send command on channel 1 to instanceId 1 of functionblock "AudioDiskPlayer"
   mostAmsOutput(1,"AudioDiskPlayer.SourceActivity.StartResult(1,On)",1);
}
```

[General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md) • [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md) • [Symbolic Identification of Messages](../CAPLfunctionsMOSTSymIDMMessage.md) • [Input Assistant](../CAPLfunctionsMOSTInputAssistant.md) • [mostParamGet](CAPLfunctionMOSTParamGet.md) • [mostParamGetData](CAPLfunctionMOSTParamGetData.md) • [mostParamGetString](CAPLfunctionMOSTParamGetString.md) • [mostParamSet](CAPLfunctionMOSTParamSet.md) • [mostParamSetData](CAPLfunctionMOSTParamSetData.md) • [mostParamSetString](CAPLfunctionMOSTParamSetString.md) • [mostMsgSet](CAPLfunctionMOSTMsgSet.md) • [output](CAPLfunctionMOSToutput.md)
