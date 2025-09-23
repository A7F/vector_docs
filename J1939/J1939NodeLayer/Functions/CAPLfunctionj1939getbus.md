# J1939GetBus

[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionj1939getbus.md)

**CAPL Functions** » **J1939** » **J1939 NL** » J1939GetBus

## Function Syntax

```
dword J1939GetBus( char[] busName );
```

## Description

This function returns a bus handle.

## Parameters

- **busName**: bus name or "default"

## Return Values

bus handle or 0 if bus name is unknown

## Example

```c
dword busHandle;

busHandle = J1939GetBus( "ImplementBus" );
```
