[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionOnTimer.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Event Procedures](../CAPLfunctionsEventProceduresOverview.md) » on timer

# on timer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

You can define time events in CAPL. When this event occurs, i.e. when a certain period of time elapses, the associated `on timer` procedure is called. You can program cyclic program sequences by resetting the same time event within the `on timer` procedure.

The timer variable can be accessed with the key word [this](CAPLfunctionKeywordThis.md) within the event procedure.

You would start a previously-defined timer with the function [setTimer](../Functions/CAPLfunctionSetTimer.md).

In CAPL exists the following variable types for timer:

- **timer** - timer based on seconds
- **msTimer** - timer based on milliseconds

After the timer has elapsed, the associated `on timer` procedure is called. The maximum time is 2147483647 s (=596523.23h) for variables of the type timer and 2147483647 ms (= 2147483,647 s = 596,52h) for variables of the type **msTimer**. With the function [cancelTimer](../Functions/CAPLfunctionCancelTimer.md) you can stop a timer which has already been started and thereby prevent the associated on timer procedure from being called.

**Note**

If several CAPL timers elapse to the exact same time:

- all timers will be executed
- the event procedures of these timers will be operated in an undefined sequence

**Example**

After pressing key 'a' in the following example timer is set and after 20 milliseconds a timer callback is raised:

```plaintext
msTimer myTimer;
message 100 msg;
...
on key 'a' {
   setTimer(myTimer,20);
}
...
on timer myTimer
{ 
   output(msg);
}
```

## Version Extensions

**Version 7.2**

Since version **7.2**, you can retrieve the name of the timer as a string constant with `this.name`.

**Version 7.5**

Since version **7.5** you can save timers in an array.

**Example**

```plaintext
variables
{
   mstimer myTimers[10];
}
```

You have to set each single timer but the same timer procedure will be called for all timers. For that the procedure has to contain a parameter (**dword** type) that indicates the index of the just run out timer.

**Example**

```plaintext
on start
{
   dword i;
   for (i = 0; i < elcount(myTimers); ++i)
      myTimers[i].set(100 + 20 * i);
}

on timer myTimers(dword index)
{
   // ...
}
```

In the procedure the keyword **this** describes the whole array. E.g. if you want to set the just run out timer, you have to add an index to **this**.

**Example**

```plaintext
write("Timer %s with index %d fired", this[index].name, index);
setTimer(this[index], 2000);
```

[Class: Timer, MsTimer](../../ObjectOrientedProg/CAPLfunctionsOOPTimer.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
