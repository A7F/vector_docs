# Iso11783ECUGoOffline

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783ECUGoOffline( dword ecuHandle );
```

## Description

The function switches the state of the node to offline. It does not send a cannot claim address parameter group.

After calling this function the node cannot send any parameter groups, but it is responding to requests for address claim.

Use the function [Iso11783ECUGoOnline](CAPLfunctionIso11783ECUGoOnline.md) to start the node again.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

- **0**: ok
- **2**: invalid ECU handle

## Example

```plaintext
Iso11783ECUGoOffline(ecuHdl);
```
