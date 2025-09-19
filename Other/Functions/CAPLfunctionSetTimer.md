[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetTimer.md)

**CAPL Functions** » **General** » **Function Overview** » **setTimer**

# setTimer

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void setTimer(msTimer t, long duration); // form 1`
- `void setTimer(timer t, long duration); // form 2`
- `void setTimer(timer t, long durationSec, long durationNanoSec); // form 3`

## Method Syntax (Dynamic)

- `void msTimer::set(long);`

## Description

Sets a timer.

## Parameters

Timer or msTimer variable and an expression which specifies the duration of the timer.

## Return Values

—

## Example

```plaintext
variables {
  msTimer t1;
  Timer t23;
}

on key F1 {
  setTimer(t1, 200); // set timer t1 to 200 ms
}

on key F2 {
  setTimer (t23, 2); // set timer t23 to 2 sec
}

on key F3 {
  setTimer (t23, 0, 1250*1000 ); // set timer t23 to 1.250 milliseconds
}

on timer t1 {
  write("F1 was pressed 200ms ago");
}

on timer t23 {
  write("F2 was pressed 2 sec ago or F3 1250000 nsec ago");
}
```

[Class: Timer, MS Timer](../../ObjectOrientedProg/CAPLfunctionsOOPTimer.md) • [cancelTimer](CAPLfunctionCancelTimer.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
