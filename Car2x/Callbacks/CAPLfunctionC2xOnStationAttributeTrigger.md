[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Callbacks/CAPLfunctionC2xOnStationAttributeTrigger.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » OnStationAttributeTrigger

# OnStationAttributeTrigger (Callback)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void OnStationAttributeTrigger(char attributeName[]);
```

## Description

This callback is called when the following three conditions are met:

- Scenario attribute with the name specified in `attributeName` reaches the next attribute keypoint (value assignment) in the scenario timeline;
- Scenario attribute property **Trigger** was set to true in the corresponding scenario file;
- Scenario attribute with the name specified in `attributeName` belongs to the scenario station of a calling CAPL node.

This callback is intended to define a reaction on triggerable attributes of a scenario station assigned to the calling CAPL node only. If you want only react on a attribute triggering of all stations in the scenario, please use [OnStationAttributeTriggerAll](CAPLfunctionC2xOnStationAttributeTriggerAll.md) callback function instead.

## Parameters

- `attributeName`: Name of the scenario station attribute

## Return Values

—

## Example

```plaintext
void OnStationAttributeTrigger(char attrName[])
{
  long stationHandle;
  char stationName[200];
  stationHandle = C2xGetStationHandle("%NODE_NAME%");
  if (stationHandle != 0 && C2xGetStationName(stationHandle, elCount(stationName), stationName) == 0)
  {
    // For all attributes of this station
    write("CAPL Node '%NODE_NAME%', Car2x/V2x station '%s', %f sec : OnStationAttributeTrigger called - Attribute '%s' = %f" ,
          stationName,
          TimeNowNS()/1e9 ,
          attrName,
          C2xGetStationAttributeDouble(attrName));

    // For concrete attribute of this station
    if (strncmp(attrName,"Speed",strlen(attrName)) == 0)
    {
      write("Car2x/V2x Station '%s', %f sec : OnStationAttributeTrigger called - Station Speed = %f",
            stationName,
            TimeNowNS()/1e9 ,
            C2xGetStationAttributeDouble("Speed"));
    }
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)