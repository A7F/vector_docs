# distObjInterface::CreateMonitoringObject

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

[monitoringDistObjRef](../Objects/CAPLfunctionMonitoringDistObjRef.md) <Interface> [distObjInterface](../Objects/CAPLfunctiondistObjInterface.md) <Interface>::CreateMonitoringObject(distObjBlueprint <Interface> blueprint, char path[]);

[monitoringDistObjRef](../Objects/CAPLfunctionMonitoringDistObjRef.md) reverse<<Interface>> [distObjInterface](../Objects/CAPLfunctiondistObjInterface.md) <Interface>::CreateMonitoringObject(distObjBlueprint reverse<<Interface>> blueprint, char path[]);

## Description

Creates a dynamic monitoring object from the blueprint.

**Note**: If an error occurs in a test module, the error message will be reported as an error in the test system. Otherwise, a message will be written to the CANoe DE Family Write Window.

## Parameters

- **blueprint**: Blueprint which sets the attributes and virtual networks of the dynamic monitoring object.
- **path**: Fully qualified name of the dynamic monitoring object.

## Return Values

- New dynamic monitoring object.
- Invalid monitoring object if an error occurred.

## Example

—
