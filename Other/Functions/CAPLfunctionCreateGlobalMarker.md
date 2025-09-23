# CreateGlobalMarker

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long createGlobalMarker (char markerName[], char makerDesc []);
```

## Description

Sets a [marker](../../../CANoeCANalyzer/Windows/GlobalMarkers.md) in the CANoe DE product Trace Window, Graphics Window and State Tracker. The set marker can be displayed with the shortcut menu **Show** in the marker bar of these windows.

## Parameters

- **markerName**: Name of the marker.
- **makerDesc**: Description of the marker.

## Return Values

—

## Example

```plaintext
on key 'a'
// sets a marker by pressing key <a>
{
  createGlobalMarker("speed", "speedDesc");
}
```
