[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783getbus.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783GetBus

# Iso11783GetBus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783GetBus( char[] busName );
```

## Description

This function returns a bus handle.

## Parameters

- **busName**: Bus name or "default"

## Return Values

Bus handle or 0 if bus name is unknown

## Example

```plaintext
dword busHandle;

busHandle = Iso11783GetBus( "ImplementBus" );
```
