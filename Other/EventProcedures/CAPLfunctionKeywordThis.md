[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionKeywordThis.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Event Procedures](../CAPLfunctionsEventProceduresOverview.md) » Keyword this

# Keyword this

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

Within an [event procedure](../../../Shared/CAPL/General/EventProceduresOverview.md) for receiving a CAN object or a variable, the data structure of the object is designated by the key word **this**.

For example, you could access the first data byte of message 100 which was just received by means of the following:

```plaintext
on message 100 {
    byte byte_0;
    byte_0 = this.byte(0);
    ...
}
```

Analogously, you could read the new value of the integer variable **Switch** which has just been changed by means of the following:

```plaintext
on sysVar Switch {
    int val;
    val = @this;
    ...
}
```

> **Note**  
> You should not change the value of **this** within an event procedure. However, to permit the use of this as a parameter, value changes made to **this** are not prohibited by the CAPL compiler. However, please note that these types of write accesses to **this** are only valid locally (i.e. within the event procedure). When compiling you will receive an appropriate warning. Thus, if you call the function [output(this)](../../CAN/Functions/CAPLfunctionOutput.md) after **this** has been changed in an [on message](../../CAN/EventProcedures/CAPLfunctionOnMessage.md) event procedure, the unchanged original of **this** is passed, and not your change.

## Special Case: Output of signal values using this

```plaintext
on message 101
{
    float a = 0;
    a = this.Signal1.phys;
}
```

> **Note**  
> For a signal length of more than 32 bit the read out of signal values from a message with **this.&lt;signalName&gt;** is not yet supported. In this case the dollar notation must be used, see the example below.

```plaintext
on message 101
{
    float a = 0;
    a = $Signal1;
}
```

[Access to signal values using this](../../CAN/EventProcedures/CAPLfunctionOnMessage.md) • [Selectors](../../../Shared/CAPL/General/SelectorsOverview.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
