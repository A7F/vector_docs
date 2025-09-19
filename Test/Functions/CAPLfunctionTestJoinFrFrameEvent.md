[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinFrFrameEvent.md)

**CAPL Functions** » **Test Feature Set** » **TestJoinFrFrameEvent**

# TestJoinFrFrameEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinFrFrameEvent (dbFrFrame aFrame)`
- `long TestJoinFrFrameEvent (dword aSlotId, dword aBaseCycle, dword aCycleRepetition, dword aChannelMask)`

## Description

Completes the current set of "joined events" with the transmitted event. This function does not wait.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFrame**: Frame to be awaited as it is defined in the database.
- **aSlotId**: Numeric slot identifier. Value range: 1...2047
- **aBaseCycle**: Numeric base cycle. This value must be less than the repetition factor. Together with the repetition factor this value determines the "Cycle Multiplexing". Value range: 0...63
- **aCycleRepetition**: Cycle repetition factor. Together with the base cycle this value determines the "Cycle Multiplexing". Value has to be a power to 2 (1, 2, 4, 8, 16, 32 or 64).
- **aChannelMask**: Channel of the transmission message. Values:
  - 1: Channel A
  - 2: Channel B
  - 3: Channel A+B

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

For an example see function [TestWaitForFrFrame](CAPLfunctionTestWaitForFrFrame.md).

[TestWaitForFrFrame](CAPLfunctionTestWaitForFrFrame.md) • [TestGetWaitFrFrameData](CAPLfunctionTestGetWaitFrFrameData.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
