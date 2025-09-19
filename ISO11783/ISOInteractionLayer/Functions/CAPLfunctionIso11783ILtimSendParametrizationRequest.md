[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSendParametrizationRequest.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_TIMSendParametrizationRequest**

# Iso11783IL_TIMSendParametrizationRequest

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMSendParametrizationRequest(byte functionId, byte serverAddress);` // form 1
- `long Iso11783IL_TIMSendParametrizationRequest(dbNode client, byte functionId, byte serverAddress);` // form 2

## Description

The function sends a parametrization request (server capabilities clarification request) for a function to the TIM server.

You can define the content of the parameterization request by [Iso11783IL_TIMExtendParametrizationRequest](CAPLfunctionIso11783ILtimExtendParametrizationRequest.md) and [Iso11783IL_TIMClearParametrizationRequest](CAPLfunctionIso11783ILtimClearParametrizationRequest.md).

## Parameters

- **functionId**: Function ID of the TIM function.
  - 1-32 (1h-20h): Auxiliary Value 1 – 32
  - 64 (40h): Front PTO
  - 65 (41h): Rear PTO
  - 66 (42h): Front hitch
  - 67 (43h): Rear hitch
  - 68 (44h): Vehicle speed
  - 70 (46h): External guidance
  - 71 (47h): Front top linkage
  - 72 (48h): Rear top linkage

- **serverAddress**: The TIM client sends the Parametrization Request to the TIM server which uses this address. Value range: 0..253.

- **client**: TIM client simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-102**: Invalid address or invalid function ID

## Example

```c
void SendVehicleSpeedParametrizationRequest(byte serverAddress)
{
  long result;
  byte functionID = 68; // vehicle speed
  byte controlMode = 0; // generic info
  result = Iso11783IL_TIMExtendParametrizationRequest(functionID, controlMode);
  if (result < 0) writeEx(1, 3, "Failed to extend parametrization request");
  result = Iso11783IL_TIMSendParametrizationRequest(functionID, serverAddress);
  if (result < 0) writeEx(1, 3, "Failed to send parametrization request");
  result = Iso11783IL_TIMClearParametrizationRequest(functionID);
  if (result < 0) writeEx(1, 3, "Failed to clear parametrization request");
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
