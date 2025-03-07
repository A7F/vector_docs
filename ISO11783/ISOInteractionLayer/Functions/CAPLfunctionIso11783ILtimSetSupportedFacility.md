[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetSupportedFacility.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetSupportedFacility

# Iso11783IL_TIMSetSupportedFacility

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetSupportedFacility(char functionFacilityName[], long value); // form 1
long Iso11783IL_TIMSetSupportedFacility(dbNode server , char functionFacilityName[], long value); // form 2
```

## Description

The function sets a facility of a TIM function in a TIM server.

By means of this function you can define all possible TIM functions supported by the TIM server.

If least one facility of a function is set then the function is listed in the **TIM_FunctionsSupportResponse** message. By default the other facilities of the function are set to value **3** (**not available**).

You can use [Iso11783IL_TIMResetAllSupportedFunctions](CAPLfunctionIso11783ILtimResetAllSupportedFunctions.md) to remove all functions and all of their facilities. Then they are no longer listed in the **TIM_FunctionsSupportResponse** message.

## Parameters

- **functionFacilityName**: Name if the function facility.
  - auxiliaryValve<N>State (N = 1..32)
  - auxiliaryValve<N>Flow (N = 1..32)
  - frontPTODisengagement
  - frontPTOEngagementCounterClockwise
  - frontPTOEngagementClockwise
  - frontPTOSpeedCounterClockwise
  - frontPTOSpeedClockwise
  - rearPTODisengagement
  - rearPTOEngagementCounterClockwise
  - rearPTOEngagementClockwise
  - rearPTOSpeedCounterClockwise
  - rearPTOSpeedClockwise
  - frontHitchMotion
  - frontHitchPosition
  - rearHitchMotion
  - rearHitchPosition
  - vehicleSpeedForward
  - vehicleSpeedReverse
  - vehicleSpeedStartMotion
  - vehicleSpeedStopMotion
  - vehicleSpeedForwardDirection
  - vehicleSpeedReverseDirection
  - vehicleSpeedChangeOfDirection
  - externalGuidanceCurvature

- **value**: New value of the facility.
  - 0: Server does not support this facility
  - 1: Server supports this facility
  - 2: Reserved
  - 3: The facility was not defined when the server was built

- **server**: TIM server node.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)