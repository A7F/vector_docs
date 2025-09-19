[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSSetTriggerParamsEx.md)

## CAPL Functions » VT System » SetTriggerParamsEx

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

### Note
The function can only be called on system variable namespaces of appropriate channels of **VT System** modules.

### Method Syntax

```plaintext
long SysVarNamespace.SetTriggerParamsEx (eVTSTrigger Trigger, double MinPulseWidth, double RestartTime, dword PreTriggers, dword RestartTriggers, dword ThresholdEventCount, dword ExtSettings);
```

### Description
The function configures additional parameters for **VT System** triggers. Basic parameters are configured using [SetTriggerParams](CAPLfunctionVTSSetTriggerParams.md).

You can find additional information about **VT System** triggers on the page [Triggers](../../../CANoeCANalyzer/VTSystem/VTSystemTrigger.md).

### Parameters

- **Trigger**: Specifies which trigger is configured.  
  **VT1004** module: Values see [eVTSTrigger](../CAPLfunctionsVTSystemEnumeration.md#eVTSTrigger)

- **MinPulseWidth**: Specifies that the triggers fires only if no opposite edge or level event occurs within the specified time after the triggering event. This way you can restrict the trigger to pulses that take at least as long as specified with this parameter. E.g. for a trigger that detects rising edges and a **MinPulseWidth** of 0.01 a rising edge is only detected if no falling edge occurs within 10ms.  
  This parameter is transferred to the **VT System** with nanosecond resolution.  
  Valid values: 0 (0.0s)..1.0 (1.0s)

- **RestartTime**: Specifies the delay after which a trigger is restarted by another trigger.  
  This parameter is transferred to the **VT System** with nanosecond resolution.  
  Valid values: 0 (0.0s)..1.0 (1.0s)  
  **Example**: Trigger 2 is configured as a restart trigger for trigger 1. In this case trigger 1 is restarted after trigger 2 fires, with a delay that is set by this parameter.

- **PreTriggers**: This bitfield specifies preconditions for the configured trigger. Every set bit specifies a trigger that must be active before the configured trigger is activated. This setting refers to triggers of the same VT System channel.  
  Bit 0 set: Trigger1 must fire as a precondition  
  Bit 1 set: Trigger2 must fire as a precondition  
  ...  
  **VT1004** module: 8 lowermost bits can be used.  
  **Example**: Set **PreTriggers** to 5 (= 1 + 4) to use triggers 1 and 3 as preconditions for the configured trigger.

- **RestartTriggers**: This bitfield specifies the triggers that restart the configured trigger. After a restart another event can be shown by trigger event system variable of the trigger. However the event counter of the trigger is not reset. This setting refers to triggers of the same VT System channel.  
  Bit 0 set: Trigger1 restarts the configured trigger  
  Bit 1 set: Trigger2 restarts the configured trigger  
  Bit 2 set: Trigger3 restarts the configured trigger  
  ...  
  **VT1004** module: 8 lowermost bits can be used.  
  **Example**: Set **RestartTriggers** to 10 (= 2 + 8) to set triggers 2 and 4 as restart triggers for the configured trigger.

- **ThresholdEventCount**: If this parameter is set to a value k higher than 0, trigger events are only visible and the event counter for the trigger is only incremented when the triggering event has occurred k + 1 times.  
  Valid values: 0..4294967295  
  **Example**: If **ThresholdEventCount** is set to 3 the trigger event system variable is set when the configured event occurs for the 4th time. Also the event counter is incremented every 4th time the configured event occurs.

- **ExtSettings**: This bitfield specifies additional settings. Values see [eVTSTriggerEdgeType](../CAPLfunctionsVTSystemEnumeration.md#eVTSTriggerEdgeType).

### Return Values

- **0**: Successful call
- **-1**: Call error
- **-2**: The namespace on which the command was called does not exist, is not a valid **VT System** namespace or does not support this command.

### Example

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
   minPulseWidth = 0.002; // pulse must have a width of at at least 2ms

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

[vtsSetTriggerParamsEx](CAPLfunctionVTSvtsSetTriggerParamsEx.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
