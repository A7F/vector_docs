[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetRequiredFacility.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetRequiredFacility

# Iso11783IL_TIMSetRequiredFacility

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetRequiredFacility(char facilityName[], long value); // form 1
long Iso11783IL_TIMSetRequiredFacility(dbNode client, char facilityName[], long value); // form 2
```

## Description

Specifies if a TIM function facility is required by the TIM client or not.

After receiving the **Functions Support Response** message of the server, the client checks if all defined required function facilities are supported by the server. If there are facilities that are not supported, the TIM Client terminates the automation.

You can use [Iso11783IL_TIMResetAllRequiredFunctions](CAPLfunctionIso11783ILtimResetAllRequiredFunctions.md) to empty the list of necessary facilities.

## Parameters

- **facilityName**: Name of the TIM function facility.
  - auxiliaryValve`<N>`State (N = 1..32)
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
  - **0**: Facility is not required by the TIM client.
  - **1**: Facility is required by the TIM client.

- **client**: TIM client node.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)