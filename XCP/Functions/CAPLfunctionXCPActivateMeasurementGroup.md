[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPActivateMeasurementGroup.md)

[CAPL Functions](../../CAPLfunctions.md) » [XCP](../CAPLfunctionsXCPOverview.md) » xcpActivateMeasurementGroup

# xcpActivateMeasurementGroup

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long xcpActivateMeasurementGroup(char[] ecuQualifier, char[] groupName);
```

## Description

Changes the measurement group that will be used for the next connection to the XCP/CCP device.

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).
- **groupName**: Name of the measurement group.

## Return Values

- **0**: OK
- **-1**: Device with this name is not existing
- **-2**: Operation not allowed – already connected
- **-5**: `groupName` does not exist

## Example

—
