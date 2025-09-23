[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTimeDiff.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » timeDiff

# timeDiff

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long timeDiff(message m1, NOW); // from 1`
- `long timeDiff(message m1, message m2); // from 2`

## Description

Time difference between messages or between a message and the current time in ms (msg2 - msg1 or now - msg1). Starting with CANalyzer 2.xx this difference can be calculated directly (Units of 10 microseconds).

## Parameters

- Variable of type **message**
- Variable of type **now**

## Return Values

Time difference in ms.

## Example

```plaintext
diff = timeDiff(m100, now); // CANalyzer 1.x & 2.x
diff = this.time - m100.time; // CANalyzer 2.xx
```

[timeNow](CAPLfunctionTimeNow.md) • [timeNowFloat](CAPLfunctionTimeNowFloat.md)
