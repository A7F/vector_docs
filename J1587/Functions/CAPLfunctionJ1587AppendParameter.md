# J1587AppendParameter

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
byte J1587AppendParameter(J1587Message msg /*in/out*/, J1587Param param /*in*/)
```

## Description

Appends a J1587 parameter to a J1708 message.

## Parameters

- **msg**: J1708 message
- **param**: returned parameter at the given index

## Return Values

- **0**: no error
- **0x1**: A J1587Param of type PCMD not specifying a PPID cannot be appended to a J1587 message with DLC > 0 in any case.
- **0x2**: The parameter to append is of a different page than the first parameter (if yet any = DLC > 0) of the J1708 message.
- **0x3**: The parameter to append is of a different type (parameter, proprietary parameter, PCMD data) than the first parameter (if yet any = DLC > 0) of the J1708 message.
- **0x4**: The DLC of the resulting J1708 message would exceed 3825 bytes (limit for the TP!).
- **0x5**: The receiver of the parameter to append to the message is different from the receiver of the message. A (proprietary) J1708 message can only have one receiver.
- **0x6**: The data content of the J1708 message is invalid. This can be due to a mismatch between the DLC and the actual content of the message or due to a message content, from which valid parameter data cannot be deduced.
- **0xFF**: general error

## Example

```plaintext
J1587Message 50 txMsg;
J1587Param EngineSpeed txEngSpeed;
J1587Param EngineCoolantTemp txEngCool;

J1587AppendParameter(txMsg, txEngSpeed);
J1587AppendParameter(txMsg, txEngCool);

output(txMsg);
```
