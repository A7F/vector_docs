[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagvFlashActivateNetwork.md)

**CAPL Functions** » **Diagnostics** » **vFlashActivateNetwork**

# vFlashActivateNetwork

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.

See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```plaintext
void vFlashActivateNetwork();
```

## Description

Activates the FlexRay network management, if required.  
The next API call is only allowed after the CAPL callback `vFlashActivateNetworkCompleted` was called!

**Note**: This event-driven API is only needed outside of test modules or test units.

## Parameters

—

## Return Values

—

## Example

```plaintext
// ...
// Prepare flashing on FlexRay
vFlashActivateNetwork();
}
void vFlashActivateNetworkCompleted(long vFlashStatusCode)
{
  write("FlexRay network management was activated");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)