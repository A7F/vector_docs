[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsStartTrigger.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsStartTrigger

# vtsStartTrigger

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long SysVarNamespace.SetTriggerParams (eVTSTrigger Trigger, dword SourceChannel, dword EdgeType);
```

## Description

The function starts the specified trigger. It also resets the event counter system variable that is associated to the trigger to 0. To use a trigger it has to be configured using the functions [vtsSetTriggerParams](CAPLfunctionVTSvtsSetTriggerParams.md) and [vtsSetTriggerParamsEx](CAPLfunctionVTSvtsSetTriggerParamsEx.md).

You can find additional information about VT System triggers on the page [Triggers](../../../CANoeCANalyzer/VTSystem/VTSystemTrigger.md).

## Parameters

- **Target**: Name of the system variable/namespace that will be affected by this function call.
- **Trigger**: Specifies which trigger is configured. VT1004/VT1104 module: Values see [eVTSTrigger](../CAPLfunctionsVTSystemEnumeration.md#eVTSTrigger).

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid VT System namespace or does not support this command.

## Example

Example: CAPL Test Module

The following example shows how triggers can be used to measure the width of a pulse, that is the distance between the rising and falling edge of a pulse.

```plaintext
variables
{
    int64 gRiseTime = 0;
    int64 gFallTime = 0;
}

void MainTest ()
{
    MeasurePulseLength();
}

void MeasurePulseLength()
{
    dword trigger1EventCount = 0;
    dword trigger2EventCount = 0;
    int64 pulseWidth = 0;

    enum eVTSTrigger trigger = eVTSTrigger1;
    enum eVTSTriggerSourceChannel sourceChannel = eVTSTriggerSourceChannel1;
    enum eVTSTriggerEdgeType edgeType = eVTSTriggerEdgeTypeRising;
    dword preTriggers = 0;

    double minPulseWidth = 0.0;

    // configure two triggers (one for the rising and one for the falling edge)
    trigger = eVTSTrigger1;
    sourceChannel = eVTSTriggerSourceChannel1;
    edgeType = 0; // rising edge
    preTriggers = 0; // no other trigger as precondition
    minPulseWidth = 0.002; // pulse must have a width of at at least 2ms

    vtsSetTriggerParams( "VTS::IgnitionChannels", trigger, sourceChannel, edgeType);
    vtsSetTriggerParamsEx( "VTS::IgnitionChannels",  trigger, minPulseWidth, 0.0, preTriggers, 0, 0, eVTSTriggerTypeEdge);

    trigger = eVTSTrigger2;
    sourceChannel = eVTSTriggerSourceChannel1;
    edgeType = eVTSTriggerEdgeTypeFalling; // falling edge
    preTriggers = 1; // first bit set: trigger 1 must be activated as a precondition

    vtsSetTriggerParams( "VTS::IgnitionChannels",  trigger, sourceChannel, edgeType);
    vtsSetTriggerParamsEx( "VTS::IgnitionChannels",  trigger, 0.0, 0.0, preTriggers, 0, 0, eVTSTriggerTypeEdge);

    TestWaitForTimeout( 50); // wait some time to make sure the settings are transferred

    // start triggers
    trigger = eVTSTrigger1;
    vtsStartTrigger( "VTS::IgnitionChannels", trigger);
    trigger = eVTSTrigger2;
    vtsStartTrigger( "VTS::IgnitionChannels", trigger);

    // wait some time until a pulse has occurred
    TestWaitForTimeout( 1000);

    // check if pulse was detected and output pulse width
    trigger1EventCount = @sysvar::VTS::IgnitionChannels::Trigger1EventCount;
    trigger2EventCount = @sysvar::VTS::IgnitionChannels::Trigger2EventCount;

    if (trigger1EventCount > 0 && trigger2EventCount > 0)
    {
        pulseWidth = gFallTime - gRiseTime;
        Write( "Pulse width: %.3f µs", (pulseWidth/1000.0));
    }
    else
    {
        Write("No pulse detected!");
    }
}

on sysvar_update sysvar::VTS::IgnitionChannels::Trigger1Event
{
    // save time stamp of rising edge when event occurs
    gRiseTime = sysGetVariableTimeNS( this);
}

on sysvar_update sysvar::VTS::IgnitionChannels::Trigger2Event
{
    // save time stamp of falling edge when event occurs
    gFallTime = sysGetVariableTimeNS( this);
}
```

[StartTrigger](CAPLfunctionVTSStartTrigger.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)