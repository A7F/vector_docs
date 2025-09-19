# coTfsSDOAbortTest

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
long coTfsSDOAbortTest( dword noOfMsgs );
```

## Description

The function aborts the following test after the transmission of messages specified in `noOfMsgs`. If the test function sends less messages, the test is not aborted.

## Parameters

- **noOfMsgs**: Number of messages after which the test is aborted.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
coTfsSDOAbortTest(3); // stop transmission after third message
```
