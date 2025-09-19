[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForFrFrameError.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForFrFrameError**

# TestWaitForFrFrameError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForFrFrameError (dbFrFrame aFrame, dword aTimeout);`
- `long TestWaitForFrFrameError (dword aSlotId, dword aBaseCycle, dword aCycleRepetition, dword aChannelMask, dword aTimeout);`
- `long TestWaitForFrFrameError (dword aTimeout);`

## Description

Waits for the occurrence of FlexRay frame error event. Should the event not occur before the expiration of the time `aTimeout`, the wait condition is resolved nevertheless. When no frame is specified the wait condition is resolved on any FlexRay frame error event.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFrame**: Frame as it is defined in the database.
- **aSlotId**: Numeric slot identifier. Value range: 1...2047
- **aBaseCycle**: Numeric base cycle. This value must be less than the repetition factor. Together with the repetition factor this value determines the "Cycle Multiplexing". Value range: 0...63
- **aCycleRepetition**: Cycle repetition factor. Together with the base cycle this value determines the "Cycle Multiplexing". Value has to be a power to 2 (1, 2, 4, 8, 16, 32 or 64).
- **aChannelMask**: Channel of the transmission message. Values:
  - 1: Channel A
  - 2: Channel B
  - 3: Channel A+B
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

For an example see function [TestWaitForFrFrame](CAPLfunctionTestWaitForFrFrame.md) and replace all FrFrame by FrFrameError.

[TestGetWaitFrFrameErrorData](CAPLfunctionTestGetWaitFrFrameErrorData.md) • [TestJoinFrFrameErrorEvent](CAPLfunctionTestJoinFrFrameErrorEvent.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
