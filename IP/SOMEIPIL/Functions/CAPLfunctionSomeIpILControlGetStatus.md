[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpILControlGetStatus.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » SomeIpILControlGetStatus

# SomeIpILControlGetStatus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpILControlGetStatus();
```

## Description

Returns current status of SOME/IP IL.

## Parameters

—

## Return Values

- **0**: uninitialized
- **1**: initialized autostart allowed
- **2**: initialized no autostart
- **3**: initialized no autostart after prestart
- **4**: active
- **5**: stopped; suspended
- **6**: measurement stopping
- **7**: measurement ended

## Example

—

[See Also](javascript:void(0);)
