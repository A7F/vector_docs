[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStop.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » stop

# stop

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void stop();
```

## Description

Programmed interrupt of the ongoing measurement.

If the function is called in an event procedure, the event procedure will always be executed completely before the measurement is stopped.

In offline mode this function interrupts but does not end the measurement. In offline mode the measurement can only be ended with `<ESC>`.

## Parameters

—

## Return Values

—

## Example

**Example 1**

```plaintext
...
if( isExtId(this) )
    stop();
...
```

**Example 2**

stop () used in an event procedure

```plaintext
on key 'a'
{
    write ("one"); 
    write ("two"); 
    stop(); 
    write ("three"); 
}
```

Output in CANoe DE product Write Window:

```plaintext
...
CAPL / .NET one
CAPL / .NET two
CAPL / .NET three
System End of measurement 08:57:30.203 am
```

[trigger](CAPLfunctionTrigger.md)
