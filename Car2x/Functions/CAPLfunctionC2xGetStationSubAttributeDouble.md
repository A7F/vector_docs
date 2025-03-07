[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetStationSubAttributeDouble.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetStationSubAttributeDouble

# C2xGetStationSubAttributeDouble

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
float C2xGetStationSubAttributeDouble(char[] attributeName, char[] subAttributeName); // form 1
float C2xGetStationSubAttributeDouble(char[] stationName, char[] attributeName, char[] subAttributeName); // form 2
```

## Description

This function returns the actual value of the floating point typed scenario sub-attribute. Form1 of the function returns values of an attribute of the calling (current) station. Form2 allows to get values of all sub-attributes of any station in the scenario, even if the scenario station does not have an assigned databasis node.

## Parameters

- **stationName**: Scenario station name
- **attributeName**: Name of the scenario attribute which belongs to the scenario station specified by stationName parameter
- **subAttributeName**: Name of the scenario sub-attribute which belongs to the scenario station attribute specified by attributeName parameter

## Return Values

The floating point value of the attribute at the time of function call.

- **-1**: Error, specified station and/or attribute name do not exist in the scenario.

## Example

```c
void OnStartScenario()
{
  write("OnStartScenario - Station Sub Attribute = %f", C2xGetStationSubAttributeDouble("MyAttribute", "MySubAttribute"));
  write("OnStartScenario - Station Sub Attribute = %f", C2xGetStationSubAttributeDouble("Station1","MyAttribute", "MySubAttribute"));
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)