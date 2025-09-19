[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMessage.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForMessage

# TestWaitForMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForMessage(dbMsg aMessage, dword aTimeout);`
- `long TestWaitForMessage(dword aMessageId, dword aTimeout);`
- `long TestWaitForMessage(dword aTimeout);`

## Description

Waits for the occurrence of the specified message **aMessage**. Should the message not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

When no message is specified the wait condition is resolved on any message.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMessage**: Message that should be awaited
- **aMessageId**: Numeric ID of the message that should be awaited
- **aTimeout**: Maximum time that should be waited [ms]
  - (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```cpp
// waits for the occurrence of message ‚VehicleMotion’
long result;
result = TestWaitForMessage(VehicleMotion, 2000);
```

[TestJoinMessageEvent](CAPLfunctionTestJoinMessageEvent.md) • [TestGetWaitEventMsgData](CAPLfunctionTestGetWaitEventMsgData.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
