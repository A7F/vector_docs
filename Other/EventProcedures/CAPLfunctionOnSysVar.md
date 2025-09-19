[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/EventProcedures/CAPLfunctionOnSysVar.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Event Procedures](../CAPLfunctionsEventProceduresOverview.md) » on sysVar

# on sysVar

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

The event procedure type `on sysVar` is provided to react to value changes of system variables in your CANoe DE product. In contrast to messages, system variables are not blocked by CAPL nodes in the Measurement Setup. Therefore, when there are two CAPL nodes in series, both react to the same system variable with the event procedure `on sysVar`.

In the procedure `on sysVar X{ ... }` there is a reaction to the event change of system variable **X**. The system variable can be accessed by the key word [this](CAPLfunctionKeywordThis.md) within the event procedure, e.g. to determine the value of the variable with the ‘@’ syntax or the function `sysGetVariable`.  
The time stamp of the last system variable change (in nanoseconds since measurement start) can be retrieved with "**this.time_ns**".

**X** must be the fully qualified name of the system variable, i.e. the variable name preceded by all namespace names, separated by "::". The system variable must exist at compile time. Please note that the automatic make mechanism in your CANoe DE product currently does not trigger a compile whenever a system variable definition changes.

The procedure `on sysVar` is called only when the value of the variable changes. It can also be written as `on sysVar_change`. If you want to be notified of value updates to the variable which don’t change the value, you should use `on sysVar_update` instead.

You can also react in the same way to value changes of specific elements of a system variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md). For this, add the element to the name of the variable. For additional clarity, you can also use `on sysVarMember` instead of `on sysVar`.

## Example

In the following example there is a reaction to a change on the I/O input DI_0 (first input port), and the new value of the I/O signal is assigned to the signal IOValue of a CAN message transmitted by the node Gateway.

```plaintext
on sysvar IO::DI_0
{
    $Gateway::IOValue = @this;
}
```

### Note

Starting with CANoe DE version **7.1 SP4**, you can also define handlers for several system variables. For this, use the syntax "`on sysVar (sysVar1 | sysVar2 | ...)`", e.g. "`on sysVar (IO::DI_0 | IO_DI1)`". The handler is called whenever one of the system variables changes (or is updated if you use `on sysvar_update`). The keyword [this](CAPLfunctionKeywordThis.md) can only be used in such a handler if all variables have the same data type. CAPL programs which contain such handlers cannot be used with versions **< 7.1 SP4**.

Since version **7.2**, you can retrieve the name of the system variable as a string constant with **this.name** and its namespace with **this.namespace**.

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
