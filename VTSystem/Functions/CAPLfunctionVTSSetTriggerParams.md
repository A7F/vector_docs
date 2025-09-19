[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetTriggerParams.md)

**CAPL Functions** » **VT System** » **SetTriggerParams**

# SetTriggerParams

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
The function can only be called on system variable namespaces of appropriate channels of **VT System** modules.

## Method Syntax

`long SysVarNamespace.SetTriggerParams (eVTSTrigger Trigger, eVTSTriggerSourceChannel SourceChannel, eVTSTriggerEdgeType EdgeType);`

## Description

The function configures basic parameters for triggers. Further parameters can be set with the function [SetTriggerParamsEx](CAPLfunctionVTSSetTriggerParamsEx.md).

You can find additional information about **VT System** triggers on the page [Triggers](../../../CANoeCANalyzer/VTSystem/VTSystemTrigger.md).

## Parameters

- **Trigger**: Specifies which trigger is configured: Values see [eVTSTrigger](../CAPLfunctionsVTSystemEnumeration.md#eVTSTrigger)
- **SourceChannel**: Specifies to which channel the configured trigger is connected: Values see [eVTSTriggerSourceChannel](../CAPLfunctionsVTSystemEnumeration.md#eVTSTriggerSourceChannel)
- **EdgeType**: Values see [eVTSTriggerEdgeType](../CAPLfunctionsVTSystemEnumeration.md#eVTSTriggerEdgeType). If a triggered is configured to **level** type using [SetTriggerParamsEx](CAPLfunctionVTSSetTriggerParamsEx.md) this parameter sets which level is detected.

## Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.

## Example

**Example: CAPL Test Module**  
The following example shows how triggers can be used to measure the width of a pulse that is the distance between the rising and falling edge of a pulse.

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
   edgeType = eVTSTriggerEdgeTypeRising; // rising edge
   preTriggers = 0; // no other trigger as precondition
   minPulseWidth = 0.002; // pulse must have a width of at least 2ms

   sysvar::VTS::IgnitionChannels.SetTriggerParams( trigger, sourceChannel, edgeType);
   sysvar::VTS::IgnitionChannels.SetTriggerParamsEx( trigger, minPulseWidth, 0.0, preTriggers, 0, 0, eVTSTriggerTypeEdge);

   trigger = eVTSTrigger2;
   sourceChannel = eVTSTriggerSourceChannel1;
   edgeType = eVTSTriggerEdgeTypeFalling; // falling edge
   preTriggers = 1; // first bit set: trigger 1 must be activated as a precondition

   sysvar::VTS::IgnitionChannels.SetTriggerParams( trigger, sourceChannel, edgeType);
   sysvar::VTS::IgnitionChannels.SetTriggerParamsEx( trigger, 0.0, 0.0, preTriggers, 0, 0, eVTSTriggerTypeEdge);

   TestWaitForTimeout( 50); // wait some time to make sure the settings are transferred

   // start triggers
   trigger = eVTSTrigger1;
   sysvar::VTS::IgnitionChannels.StartTrigger( trigger);
   trigger = eVTSTrigger2;
   sysvar::VTS::IgnitionChannels.StartTrigger( trigger);

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

[vtsSetTriggerParams](CAPLfunctionVTSvtsSetTriggerParams.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
