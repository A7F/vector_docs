[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/CAPLfunctionsBoxedEventProceduresOverview.md)

[CAPL Functions](../CAPLfunctions.md) » [General](CAPLGeneralStartPage.md) » Unconditional (Boxed) Event Procedures

# Unconditional (Boxed) Event Procedures

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

**Note**  
The usage of "boxed" event procedures is not compatible to older versions of your CANoe DE product. They can only be used in CAPL programs with version 7.0 and higher.

Normally, the generic event procedures (e.g. [on message *](../CAN/EventProcedures/CAPLfunctionOnMessage.md)) are only called if there is no more specific event procedure in the program for the message which is received.

**Example**  

```plaintext
on message 100
{
   write("specific");
}
on message *
{
   write("generic");
}
```

If the message 100 is received, the output in the Write Window will be "specific" only.

If you want to implement an event procedure which is called always, regardless of other event procedures, you can use a "boxed" event procedure signified by **[*]**.

**Example**  

```plaintext
on message 100
{
   write("specific");
}
on message [*]
{
   write("generic");
}
```

If the message 100 is received, the output in the Write Window will be "generic" followed by "specific".

The "boxed" event procedures are always called before other, possibly more specific event procedures in the program.

**Note**  
If you implement a "boxed" event procedure in the measurement setup, you should not call `output(this)` because of the danger of transmitting the message two times, once in the "boxed" event procedure and once in the specific event procedure. Call `output(this)` only in specific event procedures and unboxed generic event procedures.

You may use a "boxed" event procedure with the following message types:

- message
- pg
- linFrame
- frSlot

[Event Procedures](../../Shared/CAPL/General/EventProceduresOverview.md)
