[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetServerCapability.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMSetServerCapability

# Iso11783IL_TIMSetServerCapability

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long Iso11783IL_TIMSetServerCapability(char parameterName[], dword parameterValue); // form 1
long Iso11783IL_TIMSetServerCapability(dbNode server , char parameterName[], dword parameterValue); // form 2
```

## Description

The function sets a capability of a TIM function in a TIM server.

By means of this function you can define capabilities of the TIM functions which can be requested by a TIM client via a parameterization request (since TIM Version 2). You can set the supported TIM version of the TIM server with [Iso11783IL_TIMSetProperty](CAPLfunctionIso11783ILtimSetProperty.md)("implementedVersion", 2).

## Parameters

- **parameterName**: Name of the function parameter. Possible values:
  - vehicleSpeedMinimumForward
  - vehicleSpeedMaximumForward
  - vehicleSpeedMinimumBackward
  - vehicleSpeedMaximumBackward
  - frontTopLinkageBaseLength
  - frontTopLinkageStrokeLength
  - rearTopLinkageBaseLength
  - rearTopLinkageStrokeLength

- **parameterValue**: New raw value of the function parameter.

- **server**: TIM server simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-102**: Invalid parameter value
- **-1202**: Invalid parameter name

## Example

```plaintext
void SetVehicleSpeedMax(double physicalValue)
{
    long result;
    dword rawValue;
    rawValue = (physicalValue * 1000) + 32128;
    result = Iso11783IL_TIMSetServerCapability(TIMClient, "vehicleSpeedMaximumForward", rawValue);
    if (result < 0)
    {
        writeEx(1, 3, "Failed to set vehicle speed maximum (forward) to %f m/s", physicalValue);
    }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
