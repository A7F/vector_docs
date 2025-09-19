[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSonlastwpreached.md)

# GNSSOnLastWpReached

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GNSS NL](../CAPLfunctionsGNSSNLOverview.md) » GNSSOnLastWpReached

## Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void GNSSOnLastWpReached();
```

## Description

This function is called when the last waypoint of the waypoint list has been reached. The GNSS receiver waits at this point until a new waypoint is inserted into the waypoint list.

## Parameters

—

## Return Values

—

## Example

```plaintext
void GNSSOnLastWpReached()
{
  write( "Last waypoint is reached" );
}
```
