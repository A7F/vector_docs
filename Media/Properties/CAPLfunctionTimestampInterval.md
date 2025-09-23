# TimestampInterval

**Valid for**: CANoe DE • CANoe4SW DE

## Property

TimestampInterval

## Description

The timestamp interval indicates the number of events between each timestamp where an event is defined by the type of the clock.

See [TimestampType](CAPLfunctionTimestampType.md): For example, for an audio clock, an event represents a sampling point, for a video clock, an event may represent the time a (full) frame is taken.

The value of this property shall be static for the duration of the life of the stream and shall be nonzero.

## Data Type

dword

## Remarks

—
