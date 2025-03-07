[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetStationAttributeInt64.md)

**CAPL Functions** » **Car2x** » **C2xGetStationAttributeInt64**

# C2xGetStationAttributeInt64

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
int64 C2xGetStationAttributeInt64(char[] attributeName); // form 1
int64 C2xGetStationAttributeInt64(char[] stationName, char[] attributeName); // form 2
```

## Description

This function returns the actual value of the integer-typed scenario attribute. Form 1 of the function returns values of an attribute of the calling (current) station. Form 2 allows to get values of all attributes of any station in the scenario, even if the scenario station does not have an assigned database node.

## Parameters

- **stationName**: Scenario station name.
- **attributeName**: Name of the scenario attribute which belongs to the scenario station specified by stationName parameter.

## Return Values

The integer value of the attribute at the time of function call.

- **-1**: Error, specified station and/or attribute name do not exist in the scenario.

## Example

```plaintext
void OnStartScenario()
{
    write("OnStartScenario - Doors locked = %d", C2xGetStationAttributeInt64("MyAttrDoorLocked"));
    write("OnStartScenario - LeftTurnAllowed = %d", C2xGetStationAttributeInt64("TrafficLightStation","Lane1State"));
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)