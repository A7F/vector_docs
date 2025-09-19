[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSsetcourse.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSSetCourse

# GNSSSetCourse

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSSetCourse( double course, double gradient )
```

## Description

This function determines the new course and the new gradient at which the GNSS receiver will continue its motion. These two values are only used in `kCourse` simulation mode (see [GNSSStartSimulation](CAPLfunctionGNSSstartsimulation.md)).

The following table describes the relationship between course and compass direction:

- **Course:** 0°  
  **Direction:** North
- **Course:** 90°  
  **Direction:** East
- **Course:** 180°  
  **Direction:** South
- **Course:** 270°  
  **Direction:** West

If this function is called, previously set waypoints (e.g. by function [GNSSAddWpMeander](CAPLfunctionGNSSaddwpmeander.md) or [GNSSAddWpRel](CAPLfunctionGNSSaddwprel.md)) are ignored.

## Parameters

- **course**: the course in degrees
- **gradient**: the inclination in degrees

## Return Values

[error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
double c = 90.0, g = 0.0;
GNSSSetCourse( c, g );
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
