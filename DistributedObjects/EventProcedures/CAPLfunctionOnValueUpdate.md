[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/EventProcedures/CAPLfunctionOnValueUpdate.md)

# on value_update

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » on value_update

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`on value_update <value>;`

## Description

The event procedure is called whenever the specified value is updated, regardless of whether the value has changed. You can use the event procedure for all values of communication objects, including e.g. signal and event values, **LatestCall** or **LatestReturn** of methods, service states, etc.

**Notes**

A value which has a struct or array data type is always updated automatically. The event procedures for all its members are called even if just one member has changed. Instead of using several event procedures for different members it is often easier to use a single event procedure for the complex value itself.

## Parameters

- **<value>**: Designates the value on which the procedure shall be called.

## Selectors

- **ChangeTimeNS**: Last time the value was changed, in nanoseconds since measurement start.  
  Type: `int64`  
  Access Limitation: Read only

- **UpdateTimeNS**: Last time the value was updated, in nanoseconds since measurement start.  
  Type: `int64`  
  Access Limitation: Read only

## Example

**Example 1**

```plaintext
on value_update MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition
{
  write("New position received: (%d,%d)", $this.x.phys, $this.y.phys);
}
```

**Example 2 for SOME/IP application object (event)**

```plaintext
Vehicle_Ethernet::CAMF::CameraObjectDetectionPSI1.TrafficSignDetection.DetectedTrafficSigns[0].SignType
{
  write("Value 'TrafficSignDetection.DetectedTrafficSigns[0].SignType' has been updated. Value: %d",$this.phys);
}
```

**Example 2 for SOME/IP application object (field)**

```plaintext
on value_update Vehicle_Ethernet::CAMF::CameraObjectDetectionPSI1.FrameRate
{
  write("Field 'CameraObjectDetectionPSI1.FrameRate' has been updated. Value: %d",$this.phys);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on value_change](CAPLfunctionOnValueChange.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)