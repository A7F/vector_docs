[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionStandardRemoteFrameRate.md)

## CAPL Functions » CAN » StandardRemoteFrameRate

### Function Syntax

```
long StandardRemoteFrameRate ()
```

### Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.StandardRemoteFrameRate
```

### Description

Returns the current rate of standard remote CAN frames of channel **x**.

Valid **x** values: 1…32

### Parameters

—

### Return Values

Current rate of standard remote CAN frames of channel **x** in messages per second.

### Example

```
write ("Rate of standard remote frames of CAN1 = %d", CAN1.StandardRemoteFrameRate);
```
