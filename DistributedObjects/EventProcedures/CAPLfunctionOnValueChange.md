# on value_change

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » on value_change

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`on value_change <value>;`

## Description

The event procedure is called whenever the specified value changes. It’s not called when the value is updated, but does not change. You can use the event procedure for all values of communication objects, including e.g. signal and event values, **LatestCall** or **LatestReturn** of methods, service states, etc.

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
on value_change MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition
{
  write("New position received: (%d,%d)", $this.x.phys, $this.y.phys);
}
```

**Example 2 for SOME/IP application object (event)**

```plaintext
Vehicle_Ethernet::CAMF::CameraObjectDetectionPSI1.TrafficSignDetection.DetectedTrafficSigns[0].SignType
{
  write("Value 'TrafficSignDetection.DetectedTrafficSigns[0].SignType' has changed. New value: %d",$this.phys);
}
```

**Example 2 for SOME/IP application object (field)**

```plaintext
on value_change Vehicle_Ethernet::CAMF::CameraObjectDetectionPSI1.FrameRate
{
  write("Field 'CameraObjectDetectionPSI1.FrameRate' has changed. New value: %d",$this.phys);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on value_update](CAPLfunctionOnValueUpdate.md)
