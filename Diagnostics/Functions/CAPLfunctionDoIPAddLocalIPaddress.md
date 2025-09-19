# DoIP_AddLocalIPaddress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Note

- If called in a tester node, an error is returned.
- The IP address given must be available in the node’s IP context, i.e. it must be configured for the simulation node at the CANoe Ethernet network, or the address must be assigned to a Windows adapter if the operating system stack is active.
- When an address is added after the initial announcement phase has passed, no automatic vehicle announcement messages are sent.

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

`long DoIP_AddLocalIPaddress(char ipAddress[])`

## Description

Adds another IP address this vehicle simulation can be reached under.

## Parameters

- **ipAddress**: Textual representation of the numeric IP address, e.g. **192.168.123.45** for an IPv4 address, or **2001::7654** for an IPv6 address.

## Return Values

- **0**: OK
- **< 0**: Error
- **Others**: reserved

## Example

```c
// The keys + an – add and remove a specific IPv6 address
on key '-'
{
  write( "[%.3f] Removing IPv6 address", timenow()/100000.0);
  DoIP_RemoveLocalIPaddress( "2001::1");
}

on key '+'
{
  write( "[%.3f] Add IPv6 address", timenow()/100000.0);
  DoIP_AddLocalIPaddress( "2001::1");
}
```

[DoIP_RemoveLocalIPaddress](CAPLfunctionDoIPRemoveLocalIPaddress.md)
