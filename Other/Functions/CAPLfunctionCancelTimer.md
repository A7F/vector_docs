[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionCancelTimer.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » cancelTimer

# cancelTimer

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void cancelTimer(msTimer t); // from 1
void cancelTimer(timer t); // from 2
```

## [Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax (Dynamic)

```plaintext
void msTimer::cancel();
```

## Description

Stops an active timer.

## Parameters

Timer or msTimer variable.

## Return Values

—

## Example

```plaintext
variables {
    msTimer takt;
    message 100 data = {dlc = 1, byte(0) = 0xFF, dir = Tx};
}
on Timer takt {
    output(data);
    setTimer(takt, 200);
}
on key F1 {
    cancelTimer(takt); // cancel timer
    write("canceled");
}
on key F2 {
    setTimer(takt, 200); // set timer to 200ms
    write("start");
}
```

[Class: Timer, MS Timer](../../ObjectOrientedProg/CAPLfunctionsOOPTimer.md) • [setTimer](CAPLfunctionSetTimer.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
