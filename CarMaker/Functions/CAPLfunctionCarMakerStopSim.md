[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CarMaker/Functions/CAPLfunctionCarMakerStopSim.md)

**CAPL Functions** » **CarMaker Interface** » **CarMaker_StopSim**

# CarMaker_StopSim

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long CarMaker_StopSim();
```

## Description

Stops the simulation in CarMaker.

## Parameters

—

## Return Values

[APO return code](../CAPLfunctionsCarMakerReturnCodes.md)

## Example

```plaintext
on stopMeasurement
{
  gErrorState = CarMaker_StopSim();
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)