[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimOnFunctionValueRequested.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMOnFunctionValueRequested

# Iso11783IL_TIMOnFunctionValueRequested

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void Iso11783IL_TIMOnFunctionValueRequested(dword functionID, 
dword requestedRawValue, 
dword& calculatedRawValue, 
dword& calculcatedExitReasonCode
dword& calculatedAutomationStatus
)
```

## Description

This callback function is called if a function request message is received for an assigned function. The Interaction Layer checks the requested value and calls this callback with the value and the exit reason code the IL would use. You can change the value and the exit reason code in the callback.

## Parameters

- **functionID**: Function ID of the TIM function.
  - **1-32 (1h-20h)**: Auxiliary Value 1 – 32 (Supported Since TIM Version: 1)
  - **64 (40h)**: Front PTO (Supported Since TIM Version: 1)
  - **65 (41h)**: Rear PTO (Supported Since TIM Version: 1)
  - **66 (42h)**: Front hitch (Supported Since TIM Version: 1)
  - **67 (43h)**: Rear hitch (Supported Since TIM Version: 1)
  - **68 (44h)**: Vehicle speed (Supported Since TIM Version: 1)
  - **70 (46h)**: External guidance (Supported Since TIM Version: 1)
  - **71 (47h)**: Front top linkage (Supported Since TIM Version: 2)
  - **72 (48h)**: Rear top linkage (Supported Since TIM Version: 2)

- **requestedRawValue**: Value which is requested by the TIM Client.

- **calculatedRawValue**: The interaction layer suggests using this function value. If you modify this value in the callback, the modified value is the new function value.

- **calculcatedExitReasonCode**: The interaction layer suggests using this exit reason code value in the responding function status message. If you modify this value in the callback, the modified exit reason code is used in the function status message.

- **calculatedAutomationStatus**: The interaction layer suggests using this automation status value in the responding function status message. If you modify this value in the callback, the modified automation status is used in the function status message.

## Return Values

—

## Example

```plaintext
void Iso11783IL_TIMOnFunctionValueRequested (
  dword fctID,
  dword requestedRawValue,
  dword& calculatedRawValue,
  dword& calculcatedExitReasonCode,
  dword& calculcatedAutomationStatus)
{
  switch (fctID)
  {
    case cRearPTO:
      if ((calculatedRawValue >= 0x0001) && (calculatedRawValue <= 0x7D7F)) // speed counter-clockwise
      {
        if (calculatedRawValue < 0x1FC0)
        {
          calculatedRawValue = 0x1FC0; // -3000 1/min
          calculcatedExitReasonCode = cReasonRemoteCommandOutOfRange;
          calculcatedAutomationStatus = cActiveLimitedLow;
        }
      }
      else if ((calculatedRawValue >= 0x7D81) && (calculatedRawValue <= 0xFAFF)) // speed clockwise
      {
        if (calculatedRawValue > 0xDB40) // 3000 1/min
        {
          calculatedRawValue = 0xDB40;
          calculcatedExitReasonCode = cReasonRemoteCommandOutOfRange;
          calculcatedAutomationStatus = cActiveLimitedHigh;
        }
      }
      break;
    case cVehicleSpeed:
      if ((calculatedRawValue >= 0x0001) && (calculatedRawValue <= 0x7D7F)) // reverse speed
      {
        if (calculatedRawValue < 0x1BD8)
        {
          calculatedRawValue = 0x1BD8;
          calculcatedExitReasonCode = cReasonRemoteCommandOutOfRange;
          calculcatedAutomationStatus = cActiveLimitedLow;
        }
      }
      else if ((calculatedRawValue >= 0x7D81) && (calculatedRawValue <= 0xFAFF)) // forward speed
      {
        if (calculatedRawValue > 0xDF25)
        {
          calculatedRawValue = 0xDF25; // 25 m/s
          calculcatedExitReasonCode = cReasonRemoteCommandOutOfRange;
          calculcatedAutomationStatus = cActiveLimitedHigh;
        }
      }
      break;
    default:
      break;
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
