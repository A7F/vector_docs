# TimestampRate

**Valid for:** CANoe DE • CANoe4SW DE

## Property

TimestampRate

## Description

This property represents the event rate. An event is defined by the type of the clock. See [TimestampType](CAPLfunctionTimestampType.md): For example, for an audio clock, an event represents a sampling point, for a video clock, an event may represent the time a (full) frame is taken.

The value of this property is expressed as a ratio. The upper 32 bits of the property value contain the numerator and the lower 32 bits contain the denominator. For example, if the timestamp rate is 44100 Hz, the ratio is 44100/1. If the timestamp rate is 29.97 fps, the ratio is 30.000/1001.

To set the value, use the [MediaSetPropertyRatio](../Functions/CAPLfunctionMediaSetPropertyRatio.md) function. To get the value, use the [MediaGetPropertyRatio](../Functions/CAPLfunctionMediaGetPropertyRatio.md) function.

## Data Type

qword

## Remarks

—

[See Also](javascript:void(0);)
