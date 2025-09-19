[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinFrPDUEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinFrPDUEvent

# TestJoinFrPDUEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestJoinFrPDUEvent (dbFrPDU aPDU)
long TestJoinFrPDUEvent ()
```

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aPDU**: PDU to be awaited as it is defined in the database.  
  Default value: wait for any PDU.

## Return Values

- **-3**: Join error.
- **-1**: General error, for example, functionality is not available.
- **> 0**: Number of the joined event.

## Example

For an example see function [TestWaitForFrPDU](CAPLfunctionTestWaitForFrPDU.md).

[TestWaitForFrPDU](CAPLfunctionTestWaitForFrPDU.md) • [TestGetWaitFrPDUData](CAPLfunctionTestGetWaitFrPDUData.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
