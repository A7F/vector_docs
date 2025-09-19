[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForVTSStateRestore.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForVTSStateRestore**

# TestWaitForVTSStateRestore

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long TestWaitForVTSStateRestore(char target[], eVTSState targetState);
```

## Method Syntax

```
long SysvarNamespace.WaitForStateRestore(eVTSState targetState);
```

## Description

By using this function you can restore the start or default state of single VT System channels or the whole VT System at once.

### State Types

The default state is the system defined initial state of a VT System channel. It can be restored by passing **eVTSStateDefault** or **0** as the **targetState** parameter.

The start state is a user defined state that can be configured and saved in the [VT System Control](../../../CANoeCANalyzer/VTSystem/VTSystemControl/VTSControl.md). It is automatically applied right after the measurement starts. It can be restored by passing **eVTSStateStart** or **1** as the **targetState** parameter.

### Settings Order

When restoring the default state of one or more channels, the settings of each channel are changed in the following order:

- **Phase 1**: Stop all running stimulations
- **Phase 2**: Deactivate any active **VT7x01** power supplies
- **Phase 3**: Set all relays to their default positions
- **Phase 4**: Reset all remaining channel settings to their respective defaults

Restoring the channels’ start states uses the following order:

- **Phase 1**: Stop all stimulations that are currently running but need to be stopped in the start state
- **Phase 2**: Open all relays that are currently closed and need to be open in the start state
- **Phase 3**: Load all waveforms configured in the start states
- **Phase 4**: Change all channel settings to match the start state settings
- **Phase 5**: Set the interconnection modes of **VT7x01** modules
- **Phase 6**: Close all relays that are currently open and need to be closed in the start state
- **Phase 7**: Start all stimulations that are currently stopped and need to be running in the start state

**Note**

- This procedure has been chosen so that restoring the state can be done as quickly and safely as possible. In addition, the effects (e.g. voltage interruptions) on connected DUTs should be minimal. Nevertheless, before using this function, you should check whether there may be undesirable effects for your specific test setup.
- Calling this function requires a few milliseconds per channel. Therefore, calling this function for a complete VT system with many modules may take some time. This is necessary to ensure that restoring the state happens in a defined and safe way.

## Parameters

- **target**: This parameter specifies which VT System channel shall be restored to the default or start state. If you want to restore the whole VT System at once, you can use **VTS** as the target (**Function** syntax) or call the method on the **sysvar::VTS** namespace (**Method** syntax).

- **targetState**: This parameter specifies the state the given VT System channel(s) shall be restored to. The following values are available:
  - eVTSStateDefault (0)
  - eVTSStateStart (1)

## Return Values

- **0**: Successful call
- **-1**: The call failed
- **-2**: The given target VT System channel does not exist
- **-3**: The given target state is invalid
- **-4**: The function wasn't called in the context of the main method of a test module. So it is not possible to wait until the setting will be taken over from the VT system. Otherwise the call was successful but it is not sure if the settings have been taken over already when the call returns.

## Example

```plaintext
testfunction StateRestoreExamples
{
  // Restore the whole VT System to the start state (function syntax)
  TestWaitForVTSStateRestore("VTS", eVTSStateStart);

  // Restore two channels to their default states (method syntax)
  sysvar::VTS::M1_VT1004.WaitForStateRestore(eVTSStateDefault);
  sysvar::VTS::M2_VT2004.WaitForStateRestore(eVTSStateDefault);
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
