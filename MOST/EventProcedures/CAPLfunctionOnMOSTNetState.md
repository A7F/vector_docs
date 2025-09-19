[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTNetState.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostNetState

# OnMostNetState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
OnMostNetState(long oldstate, long newstate);
```

## Description

The `OnMostNetState()` event procedure is called when the network status is changed. **oldstate** and **newstate** pass the previous and current network status respectively.

The following network states are defined based on the MOST Specification 2.3.

- **<0**: Error code. See [Error codes in CAPL functions](../CAPLfunctionsMOSTErrorCodes.md)
- **0**: mostNetState_Undefined - Before the first event (shortly after measurement start) the network status is unknown.
- **2**: mostNetState_PowerOff - The network interface to the MOST ring is deactivated. The Tx FOT is not emitting any light.
- **3**: mostNetState_NetInterfaceInit - The network interface is initializing, e.g. after it has been woken by "light on".
- **4**: mostNetState_ConfigNotOk - The network interface is in normal operating mode (stable lock). On application level the MOST ring is in state ConfigNotOk. ConfigNotOk is entered on device initialization or when the NetworkMaster broadcasts Configuration.Status(NotOk).
- **5**: mostNetState_ConfigOk - The network interface is in normal operating mode (stable lock). On application level the MOST ring is in state ConfigOk. ConfigOk is entered when the NetworkMaster broadcasts Configuration.Status(Ok).

**Note**: Each device or each MOST hardware forms its own network state from the perspective of a node in the MOST ring.

Within this event procedure the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter, to filter these events in nodal sequences.

In the Simulation Setup event procedures are only called if the event occurs on the channel allocated to the CAPL node.

## Parameters

- **oldstate**: Old network status.
- **newstate**: Current network status.

## Return Values

—

## Example

—

[mostGetNetState](../Functions/CAPLfunctionMOSTGetNetState.md) • [OnMostNetOn](CAPLfunctionOnMOSTNetOn.md) • [OnMostStableLock](CAPLfunctionOnMOSTStableLock.md) • [OnMostCriticalUnlock](CAPLfunctionOnMOSTCriticalUnlock.md) • [mostGetLockEx](../Functions/CAPLfunctionMOSTGetLockEx.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
