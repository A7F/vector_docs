[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTMsgSet.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostMsgSet

# mostMsgSet

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long mostMsgSet(mostAmsMessage * msg, long destAdr, char symbolicMessage[], long instId);` // form 1
- `long mostMsgSet(mostAmsMessage * msg, char symbolicMessage[], long instId);` // form 2
- `long mostMsgSet(mostAmsMessage * msg, char symbolicMessage[]);` // form 3

## Description

Populating an AMS message using the syntax from the MOST specification and the description in the XML function catalog.

PosDescription, TelLen and StreamCases are checked in addition to FunctionBlock, FunctionID and OpType.

See also [Option .MOST: Symbolic Identification of Messages](../CAPLfunctionsMOSTSymIDMMessage.md)

## Parameters

- **msg**: Message to be populated
- **destAdr**: Destination address
- **symbolicMessage**: Description of the message content in the following formats:
  - `FBlock.InstanceId.Function.OpType(Parameterlist)`
  - `FBlock.InstanceId.Function.OpType`
  - `FBlock.Function.OpType(Parameterlist)`
  - `FBlock.Function.OpType`
- **InstId**: InstanceID of the function block

## Return Values

- **0**: OK (Parameter is available)
- **\<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostParamGet](CAPLfunctionMOSTParamGet.md) • [mostParamGetData](CAPLfunctionMOSTParamGetData.md) • [mostParamGetString](CAPLfunctionMOSTParamGetString.md) • [mostParamSet](CAPLfunctionMOSTParamSet.md) • [mostParamSetString](CAPLfunctionMOSTParamSetString.md) • [mostAMSOutput](CAPLfunctionMOSTAmsOutput.md) • [output](CAPLfunctionMOSToutput.md) • [General Tips on XML Function Catalog Support in CAPL](../CAPLfunctionsMOSTXMLSupport.md) • [Symbolic Identification of Parameters](../CAPLfunctionsMOSTSymIDParam.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
