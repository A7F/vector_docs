[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTPrepareReport.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostPrepareReport

# mostPrepareReport

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
mostPrepareReport(mostAmsMessage * msgCommand, mostAmsMessage * msgReport);
```

## Description

Preparation of an AMS message as response (OpType\>=9) to a received command message (OpType\<9).

The destination address of the report message is set to the source address of the command message. The parameters FBlockId, InstId and FunctionId in msgReport are set as given by the msgCommand. Any wildcard InstId in msgCommand is transferred to a concrete value in msgReport with the help of the device’s Local FBlock list.

According to the MOST specification, the OpTypes are converted by the command into the associated report OpType:

### For Properties

- **Command OpType**: GetInterface
- **Report OpType**: Interface

- **Command OpType**: any other
- **Report OpType**: Status

### For Methods

- **Command OpType**: Start, StartResult
- **Report OpType**: Result

- **Command OpType**: GetInterface
- **Report OpType**: Interface

- **Command OpType**: Abort
- **Report OpType**: Error

- **Command OpType**: StartAck, StartResultAck
- **Report OpType**: ResultAck

- **Command OpType**: AbortAck
- **Report OpType**: ErrorAck

Messages with Ack-OpTypes contain a sender handle in the first two data bytes. This sender handle is also set in the first two data bytes of the report message.

## Parameters

- **msgCommand**: Command message to be answered.
- **msgReport**: Message that should serve as a response.

## Return Values

—

## Example

—

[mostSendError](CAPLfunctionMOSTSendError.md) • [on mostAMSMessage](../EventProcedures/CAPLfunctionOnMOSTAMSMessage.md) • [output(mostAmsMessage * msg)](CAPLfunctionMOSToutput.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
