[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTAsRegistry.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostAsRegistry

# OnMostAsRegistry

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
OnMostAsRegistry();
```

## Description

When the Local FBlockList or Bus Registry is changed, the event procedure `OnMostAsRegistry()` is called.

Causes for a change to the Local FBlockList:

- Registration or unregistration of one or more function blocks
- Change to the InstID of a function block by the NetworkMaster (NetBlock.FBlockIDs.SetGet).

Causes for a change to the Bus Registry:

- In a device with NetworkMaster: Change in network status
- In a device without NetworkMaster: Receipt of the NetworkMaster.CentralRegisrty.Status message

Within this event procedure, the functions [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md), and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) can be used to call up supplemental information.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter to filter these events in nodal sequences.

In the Simulation Setup, event procedures are only called if the event occurs on the channel allocated to the CAPL node.

## Parameters

- **regsel**
  - 1: Changes in [Local FBlockList](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketLocalFBlockList.md)
  - 2: Changes in [Bus Registry](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketBusRegistry.md)

## Return Values

—

## Example

Read-Out of the Registries

In the following example, whenever a registry changes, its contents are output to the Write Window.

```plaintext
OnMostAsRegistry(long regsel)
{
    long size, i;
    long rxtxlog, fblockid, instid;
    // display registry type
    if(regsel == 1)
        write("Local Registry:");
    else if(regsel == 2)
        write("Bus Registry:");
    // get registry size
    size = mostAsRgGetSize(regsel);
    // print the whole registry
    write("Adr  FBlock InstID");
    for(i = 0; i < size; ++i)
    {
        rxtxlog = mostAsRgGetRxTxLog(regsel,i);
        fblockid = mostAsRgGetFBlockID(regsel,i);
        instid = mostAsRgGetInstID(regsel,i);
        write("%04X  %02X    %02X", rxtxlog, fblockid, instid);
    }
}
Bus Registry:
Adr FBlock InstID
0100 02 00
0100 04 01
0100 C0 01
0101 C1 01
0101 C5 01
```

[mostAsRgGetSize](../Functions/CAPLfunctionMOSTAsRgGetSize.md) • [mostAsRgGetRxTxLog](../Functions/CAPLfunctionMOSTAsRgGetRxTxLog.md) • [mostAsRgGetFBlockID](../Functions/CAPLfunctionMOSTAsRgGetFBlockID.md) • [mostAsRgGetInstID](../Functions/CAPLfunctionMOSTAsRgGetInstID.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)