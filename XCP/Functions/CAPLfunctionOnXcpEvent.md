# OnXcpEvent

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
void OnXcpEvent(char ecuQualifier[], byte data[], long dataSize);
```

## Description

This callback provides access to data that is sent from an XCP or CCP slave in an Event packet. The first data byte contains the type of the Event (named **Code** in the XCP specification).

## Parameters

- **ecuQualifier**: Name of the device, configured within the CANoe DE Family [XCP/CCP Window](../../../CANoeCANalyzer/AMDXCP/XCPConfiguration.md).
- **data**: Byte array with the event data.
- **dataSize**: Size of the event data.

## Return Values

—

## Example

—
