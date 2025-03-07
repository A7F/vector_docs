[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinFrStartCycleEvent.md)

**CAPL Functions** » **Test Feature Set** » **TestJoinFrStartCycleEvent**

# TestJoinFrStartCycleEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinFrStartCycleEvent (dword aCycle)`
- `long TestJoinFrStartCycleEvent (dword aBaseCycle, dword aCycleRepetition)`

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aCycle**: Numeric cycle identifier.  
  Value range: 0...63

- **aBaseCycle**: Numeric base cycle. This value must be less than the repetition factor. Together with the repetition factor this value determines the "Cycle Multiplexing".  
  Value range: 0...63

- **aCycleRepetition**: Cycle repetition factor. Together with the base cycle this value determines the "Cycle Multiplexing".  
  Value has to be a power to 2 (1, 2, 4, 8, 16, 32 or 64).

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

For an example see function [TestWaitForFrStartCycle](CAPLfunctionTestWaitForFrStartCycle.md).

[TestWaitForFrStartCycle](CAPLfunctionTestWaitForFrStartCycle.md) • [TestGetWaitFrStartCycleData](CAPLfunctionTestGetWaitFrStartCycleData.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)