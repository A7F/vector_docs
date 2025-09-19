[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/CAPLfunctionsVTSystemOverview.md)

[CAPL Functions](../CAPLfunctions.md) » VT System CAPL Functions

# VT System CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## VT System

The methods/functions listed on this site can only be called in connection with system variables. Information about the differences between **methods** and **functions** can be found [here](CAPLfunctionsVTSystemAlternativeFunctions.md).

**ON THIS PAGE:**

- [General Methods/Functions](#General)
- [Trigger Methods/Functions](#Trigger)
- [VT1004/VT1104 related Methods/Functions](#VT1004)
- [VT2004 related Methods/Functions](#VT2004)
- [VT2516 Methods/Functions](#VT2516)
- [VT2808 related Methods/Functions](#VT2808)
- [VT2816 related Methods/Functions](#VT2816)
- [VT2832 related Methods/Functions](#VT2838)
- [VT2848 related Methods/Functions](#VT2848)
- [VT7001 related Methods/Functions](#VT7001)
- [VT8006/VT8012 related Functions](#VT8006)

## General Methods/Functions [▲ back](#Shortcuts)

- [SetTransferCycle](Functions/CAPLfunctionVTSSetTransferCycle.md)
- [vtsSetTransferCycle](Functions/CAPLfunctionVTSvtsSetTransferCycle.md)
  - Sets the cycle time for retrieving the corresponding value from the VT System.

- [TestWaitForVTSStateRestore](../Test/Functions/CAPLfunctionTestWaitForVTSStateRestore.md)
  - Restores the default or start state of VT System channels.

## Trigger Methods/Function [▲ back](#Shortcuts)

- [SetTriggerParams](Functions/CAPLfunctionVTSSetTriggerParams.md)
- [vtsSetTriggerParams](Functions/CAPLfunctionVTSvtsSetTriggerParams.md)
  - Configures basic parameters for triggers.

- [SetTriggerParamsEx](Functions/CAPLfunctionVTSSetTriggerParamsEx.md)
- [vtsSetTriggerParamsEx](Functions/CAPLfunctionVTSvtsSetTriggerParamsEx.md)
  - Configures additional parameters for VT System triggers.

- [StartTrigger](Functions/CAPLfunctionVTSStartTrigger.md)
- [vtsStartTrigger](Functions/CAPLfunctionVTSvtsStartTrigger.md)
  - Starts the specified trigger. It also resets the event counter system variable that is associated to the trigger to 0.

## VT1004/VT1104 related Methods/Functions [▲ back](#Shortcuts)

- [ResetMinMax](Functions/CAPLfunctionVTSResetMinMax.md)
- [vtsResetMinMax](Functions/CAPLfunctionVTSvtsResetMinMax.md)
  - Resets the minimum and maximum value.

- [SetLoadMode](Functions/CAPLfunctionVTSSetLoadMode.md)
- [vtsSetLoadMode](Functions/CAPLfunctionVTSvtsSetLoadMode.md)
  - Sets the mode for internal load.

- [SetMeasurementMode](Functions/CAPLfunctionVTSSetMeasurementMode.md)
- [vtsSetMeasurementMode](Functions/CAPLfunctionVTSvtsSetMeasurementMode.md)
  - Sets the mode for voltage measurement.

- [SetLoadControlTimeout](Functions/CAPLfunctionVTSSetLoadControlTimeout.md)
- [vtsSetLoadControlTimeout](Functions/CAPLfunctionVTSvtsSetLoadControlTimeout.md)
  - Sets the timeout for the internal load.

- [SetPWMMeasurementDuration](Functions/CAPLfunctionVTSSetPWMMeasurementDuration.md)
- [vtsSetPWMMeasurementDuration](Functions/CAPLfunctionVTSvtsSetPWMMeasurementDuration.md)
  - Sets the PWM evaluation raster.

- [SetPWMThreshold](Functions/CAPLfunctionVTSSetPWMThreshold.md)
- [vtsSetPWMThreshold](Functions/CAPLfunctionVTSvtsSetPWMThreshold.md)
  - Sets the PWM trigger threshold.

- [SetImpedanceMode](Functions/CAPLfunctionVTSSetImpedanceMode.md)
- [vtsSetImpedanceMode](Functions/CAPLfunctionVTSvtsSetImpedanceMode.md)
  - Switches for VT1004A between the mode with high impedance (default state) and low impedance.

- [SetIntegrationTime](Functions/CAPLfunctionVTSSetIntegrationTime.md)
- [vtsSetIntegrationTime](Functions/CAPLfunctionVTSvtsSetIntegrationTime.md)
  - Sets the integration time for average and RMS values.

## VT2004 related Methods/Functions [▲ back](#Shortcuts)

- [LoadWFResistance](Functions/CAPLfunctionVTSLoadWFResistance.md)
- [vtsLoadWFResistance](Functions/CAPLfunctionVTSvtsLoadWFResistance.md)
  - Loads a resistance curve for a channel from a specified file.

- [LoadWFVoltage](Functions/CAPLfunctionVTSLoadWFVoltage.md)
- [vtsLoadWFVoltage](Functions/CAPLfunctionVTSvtsLoadWFVoltage.md)
  - Loads a voltage curve for a channel from a specified file.

- [SetCurveType](Functions/CAPLfunctionVTSSetCurveType.md)
- [vtsSetCurveType](Functions/CAPLfunctionVTSvtsSetCurveType.md)
  - Sets the mode of the curve.

- [SetStimulationMode](Functions/CAPLfunctionVTSSetStimulationMode.md)
- [vtsSetStimulationMode](Functions/CAPLfunctionVTSvtsSetStimulationMode.md)
  - Sets stimulation mode.

- [StartStimulation](Functions/CAPLfunctionVTSStartStimulation.md)
- [vtsStartStimulation](Functions/CAPLfunctionVTSvtsStartStimulation.md)
  - Starts stimulation output.

- [StopStimulation](Functions/CAPLfunctionVTSStopStimulation.md)
- [vtsStopStimulation](Functions/CAPLfunctionVTSvtsStopStimulation.md)
  - Stops stimulation output.

- [SetPWMResistanceLow](Functions/CAPLfunctionVTSSetPWMResistanceLow.md)
- [vtsSetPWMResistanceLow](Functions/CAPLfunctionVTSvtsSetPWMResistanceLow.md)
  - Sets the resistance value for low on PWM output.

- [SetPWMStartDelay](Functions/CAPLfunctionVTSSetPWMStartDelay.md)
- [vtsSetPWMStartDelay](Functions/CAPLfunctionVTSvtsSetPWMStartDelay.md)
  - Sets the delay of the start for the output of PWM signals and curves.

- [SetPWMResistanceHigh](Functions/CAPLfunctionVTSSetPWMResistanceHigh.md)
- [vtsSetPWMResistanceHigh](Functions/CAPLfunctionVTSvtsSetPWMResistanceHigh.md)
  - Sets the resistance value for high on PWM output.

- [SetPWMVoltageLow](Functions/CAPLfunctionVTSSetPWMVoltageLow.md)
- [vtsSetPWMVoltageLow](Functions/CAPLfunctionVTSvtsSetPWMVoltageLow.md)
  - Sets the low voltage on PWM output.

- [SetPWMVoltageHigh](Functions/CAPLfunctionVTSSetPWMVoltageHigh.md)
- [vtsSetPWMVoltageHigh](Functions/CAPLfunctionVTSvtsSetPWMVoltageHigh.md)
  - Sets the high voltage on PWM output.

- [SetPWMRepeats](Functions/CAPLfunctionVTSSetPWMRepeats.md)
- [vtsSetPWMRepeats](Functions/CAPLfunctionVTSvtsSetPWMRepeats.md)
  - Sets the number of stimulated PWM periods after the start of stimulation.

- [SetWFParams](Functions/CAPLfunctionVTSSetWFParams.md)
- [vtsSetWFParams](Functions/CAPLfunctionVTSvtsSetWFParams.md)
  - Configures the parameters for the output of a voltage or resistance curve.

## VT2516 Methods/Functions [▲ back](#Shortcuts)

- [LoadWFBitStream](Functions/CAPLfunctionVTSLoadWFBitStream.md)
- [vtsLoadWFBitStream](Functions/CAPLfunctionVTSvtsLoadWFBitStream.md)
  - The function loads a bitstream for the channel from the specified file.

- [SetCurveType](Functions/CAPLfunctionVTSSetCurveType.md)
- [vtsSetCurveType](Functions/CAPLfunctionVTSvtsSetCurveType.md)
  - Sets the mode of the bitstream.

- [SetIntegrationTime](Functions/CAPLfunctionVTSSetIntegrationTime.md)
- [vtsSetIntegrationTime](Functions/CAPLfunctionVTSvtsSetIntegrationTime.md)
  - Sets the integration time for average values.

- [SetPWMMeasurementDuration](Functions/CAPLfunctionVTSSetPWMMeasurementDuration.md)
- [vtsSetPWMMeasurementDuration](Functions/CAPLfunctionVTSvtsSetPWMMeasurementDuration.md)
  - Sets the max evaluation time for PWM signals.

- [SetPWMRepeats](Functions/CAPLfunctionVTSSetPWMRepeats.md)
- [vtsSetPWMRepeats](Functions/CAPLfunctionVTSvtsSetPWMRepeats.md)
  - Sets the number of stimulated PWM periods after the start of stimulation.

- [SetPWMVoltageHigh](Functions/CAPLfunctionVTSSetPWMVoltageHigh.md)
- [vtsSetPWMVoltageHigh](Functions/CAPLfunctionVTSvtsSetPWMVoltageHigh.md)
  - Sets the high voltage on digital output.

- [SetPWMVoltageLow](Functions/CAPLfunctionVTSSetPWMVoltageLow.md)
- [vtsSetPWMVoltageLow](Functions/CAPLfunctionVTSvtsSetPWMVoltageLow.md)
  - Sets the low voltage on digital output.

- [SetStimulationMode](Functions/CAPLfunctionVTSSetStimulationMode.md)
- [vtsSetStimulationMode](Functions/CAPLfunctionVTSvtsSetStimulationMode.md)
  - Sets stimulation mode.

- [SetThreshold1_8](Functions/CAPLfunctionVTSSetThreshold18.md)
- [vtsSetThreshold1_8](Functions/CAPLfunctionVTSvtsSetThreshold18.md)
  - Sets the threshold value for differentiating between high and low levels of the channels 1…8 of a digital module VT2516.

- [SetThreshold9_16](Functions/CAPLfunctionVTSSetThreshold916.md)
- [vtsSetThreshold9_16](Functions/CAPLfunctionVTSvtsSetThreshold916.md)
  - Sets the threshold value for differentiating between high and low levels of the channels 9…16 of a digital module VT2516.

- [SetWFParams](Functions/CAPLfunctionVTSSetWFParams.md)
- [vtsSetWFParams](Functions/CAPLfunctionVTSvtsSetWFParams.md)
  - Configures the parameters for the output of a bitstream.

- [StartStimulation](Functions/CAPLfunctionVTSStartStimulation.md)
- [vtsStartStimulation](Functions/CAPLfunctionVTSvtsStartStimulation.md)
  - Starts stimulation output.

- [StopStimulation](Functions/CAPLfunctionVTSStopStimulation.md)
- [vtsStopStimulation](Functions/CAPLfunctionVTSvtsStopStimulation.md)
  - Stops stimulation output.

## VT2808 related Methods/Functions [▲ back](#Shortcuts)

- [ResetMinMax](Functions/CAPLfunctionVTSResetMinMax.md)
- [vtsResetMinMax](Functions/CAPLfunctionVTSvtsResetMinMax.md)
  - Resets the minimum and maximum value.

- [SetMinCurrentMeasurementRange](Functions/CAPLfunctionVTSSetMinCurrentMeasurementRange.md)
- [vtsSetMinCurrentMeasurementRange](Functions/CAPLfunctionVTSvtsSetMinCurrentMeasurementRange.md)
  - Sets the current measurement range that should be used from the automatic measuring range changeover of the VT2808 module.

## VT2816 related Methods/Functions [▲ back](#Shortcuts)

- [LoadWFVoltage](Functions/CAPLfunctionVTSLoadWFVoltage.md)
- [vtsLoadWFVoltage](Functions/CAPLfunctionVTSvtsLoadWFVoltage.md)
  - Loads a voltage curve for a channel from a specified file.

- [ResetMinMax](Functions/CAPLfunctionVTSResetMinMax.md)
- [vtsResetMinMax](Functions/CAPLfunctionVTSvtsResetMinMax.md)
  - Resets the minimum and maximum value.

- [SetCurveType](Functions/CAPLfunctionVTSSetCurveType.md)
- [vtsSetCurveType](Functions/CAPLfunctionVTSvtsSetCurveType.md)
  - Sets the mode of the bitstream.

- [SetIntegrationTime](Functions/CAPLfunctionVTSSetIntegrationTime.md)
- [vtsSetIntegrationTime](Functions/CAPLfunctionVTSvtsSetIntegrationTime.md)
  - Sets the integration time for average and RMS values.

- [SetMeasurementMode](Functions/CAPLfunctionVTSSetMeasurementMode.md)
- [vtsSetMeasurementMode](Functions/CAPLfunctionVTSvtsSetMeasurementMode.md)
  - Sets the mode for voltage measurement.

- [SetOutputRange](Functions/CAPLfunctionVTSSetOutputRange.md)
- [vtsSetOutputRange](Functions/CAPLfunctionVTSvtsSetOutputRange.md)
  - Sets the range that is used for analog output on output channels of VT2816 modules.

- [SetWFParams](Functions/CAPLfunctionVTSSetWFParams.md)
- [vtsSetWFParams](Functions/CAPLfunctionVTSvtsSetWFParams.md)
  - Configures the parameters for the output of a bitstream.

- [StartStimulation](Functions/CAPLfunctionVTSStartStimulation.md)
- [vtsStartStimulation](Functions/CAPLfunctionVTSvtsStartStimulation.md)
  - Starts stimulation output.

- [StopStimulation](Functions/CAPLfunctionVTSStopStimulation.md)
- [vtsStopStimulation](Functions/CAPLfunctionVTSvtsStopStimulation.md)
  - Stops stimulation output.

## VT2832 related Methods/ Functions [▲ back](#Shortcuts)

- [SetOutputMask](Functions/CAPLfunctionVTSSetOutputMask.md)
- [vtsSetOutputMask](Functions/CAPLfunctionVTSvtsSetOutputMask.md)
  - Activates the requested rows of a switch matrix module for dynamic stimulation.

## VT2848 related Methods/Functions [▲ back](#Shortcuts)

- [LoadWFBitStream](Functions/CAPLfunctionVTSLoadWFBitStream.md)
- [vtsLoadWFBitStream](Functions/CAPLfunctionVTSvtsLoadWFBitStream.md)
  - The function loads a bitstream for the channel from the specified file.

- [SetCurveType](Functions/CAPLfunctionVTSSetCurveType.md)
- [vtsSetCurveType](Functions/CAPLfunctionVTSvtsSetCurveType.md)
  - Sets the mode of the bitstream.

- [SetOutputMode](Functions/CAPLfunctionVTSSetOutputMode.md)
- [vtsSetOutputMode](Functions/CAPLfunctionVTSvtsSetOutputMode.md)
  - Sets the mode for output on the channel.

- [SetOutputSource](Functions/CAPLfunctionVTSSetOutputSource.md)
- [vtsSetOutputSource](Functions/CAPLfunctionVTSvtsSetOutputSource.md)
  - Sets the source for the high voltage level for output.

- [SetPWMMeasurementDuration](Functions/CAPLfunctionVTSSetPWMMeasurementDuration.md)
- [vtsSetPWMMeasurementDuration](Functions/CAPLfunctionVTSvtsSetPWMMeasurementDuration.md)
  - Sets the max evaluation time for PWM signals.

- [SetPWMRepeats](Functions/CAPLfunctionVTSSetPWMRepeats.md)
- [vtsSetPWMRepeats](Functions/CAPLfunctionVTSvtsSetPWMRepeats.md)
  - Sets the number of stimulated PWM periods after the start of stimulation.

- [SetPWMStartDelay](Functions/CAPLfunctionVTSSetPWMStartDelay.md)
- [vtsSetPWMStartDelay](Functions/CAPLfunctionVTSvtsSetPWMStartDelay.md)
  - Sets the delay of the start for the output of PWM signals and curves.

- [SetThreshold](Functions/CAPLfunctionVTSSetThreshold.md)
- [vtsSetThreshold](Functions/CAPLfunctionVTSvtsSetThreshold.md)
  - Sets the threshold value for differentiating between high and low levels of a group of channels on a VT2848 module.

- [SetWFParams](Functions/CAPLfunctionVTSSetWFParams.md)
- [vtsSetWFParams](Functions/CAPLfunctionVTSvtsSetWFParams.md)
  - Configures the parameters for the output of a bitstream.

- [StartStimulation](Functions/CAPLfunctionVTSStartStimulation.md)
- [vtsStartStimulation](Functions/CAPLfunctionVTSvtsStartStimulation.md)
  - Starts stimulation output.

- [StopStimulation](Functions/CAPLfunctionVTSStopStimulation.md)
- [vtsStopStimulation](Functions/CAPLfunctionVTSvtsStopStimulation.md)
  - Stops stimulation output.

## VT7001 related Methods/Functions [▲ back](#Shortcuts)

- [\<OnSerialError>](Functions/CAPLfunctionVTSOnSerialError.md)
  - Is called when an error has occurred in an operation on a serial port.

- [\<OnSerialReceive>](Functions/CAPLfunctionVTSOnSerialReceive.md)
  - Is called when data has been received from the assigned serial port.

- [\<OnSerialSend>](Functions/CAPLfunctionVTSOnSerialSend.md)
  - Is called when a send operation has been completed on the assigned serial port.

- [LoadWFVoltage](Functions/CAPLfunctionVTSLoadWFVoltage.md)
- [vtsLoadWFVoltage](Functions/CAPLfunctionVTSvtsLoadWFVoltage.md)
  - Loads a control voltage curve for a power supply from a specified file.

- [ResetMinMax](Functions/CAPLfunctionVTSResetMinMax.md)
- [vtsResetMinMax](Functions/CAPLfunctionVTSvtsResetMinMax.md)
  - Resets the minimum and maximum value.

- [SerialClose](Functions/CAPLfunctionVTSSerialClose.md)
- [vtsSerialClose](Functions/CAPLfunctionVTSvtsSerialClose.md)
  - Closes the serial port of the VT System channel.

- [SerialConfigure](Functions/CAPLfunctionVTSSerialConfigure.md)
- [vtsSerialConfigure](Functions/CAPLfunctionVTSvtsSerialConfigure.md)
  - Configures the serial port of the VT System channel.

- [SerialOpen](Functions/CAPLfunctionVTSSerialOpen.md)
- [vtsSerialOpen](Functions/CAPLfunctionVTSvtsSerialOpen.md)
  - Opens the serial port of the VT System channel.

- [SerialReceive](Functions/CAPLfunctionVTSSerialReceive.md)
- [vtsSerialReceive](Functions/CAPLfunctionVTSvtsSerialReceive.md)
  - Receives blocks of bytes from the serial port.

- [SerialSend](Functions/CAPLfunctionVTSSerialSend.md)
- [vtsSerialSend](Functions/CAPLfunctionVTSvtsSerialSend.md)
  - Sends a block of bytes to the serial port.

- [SetIntegrationTime](Functions/CAPLfunctionVTSSetIntegrationTime.md)
- [vtsSetIntegrationTime](Functions/CAPLfunctionVTSvtsSetIntegrationTime.md)
  - Sets the integration time for average values.

- [SetInterconnectionMode](Functions/CAPLfunctionVTSSetInterconnectionMode.md)
- [vtsSetInterconnectionMode](Functions/CAPLfunctionVTSvtsSetInterconnectionMode.md)
  - Sets the mode for interconnection of the three possible power supplies and the two power outputs of the power module VT7001.

- [SetMaxCurrentMode](Functions/CAPLfunctionVTSSetMaxCurrentMode.md)
- [vtsSetMaxCurrentMode](Functions/CAPLfunctionVTSvtsSetMaxCurrentMode.md)
  - Sets the mode for the control voltage output to control the power supply's maximal output current.

- [SetMinCurrentMeasurementRange](Functions/CAPLfunctionVTSSetMinCurrentMeasurementRange.md)
- [vtsSetMinCurrentMeasurementRange](Functions/CAPLfunctionVTSvtsSetMinCurrentMeasurementRange.md)
  - Sets the current measurement range that should be used from the automatic measuring range changeover of the VT7001 module.

- [SetRefVoltageMode](Functions/CAPLfunctionVTSSetRefVoltageMode.md)
- [vtsSetRefVoltageMode](Functions/CAPLfunctionVTSvtsSetRefVoltageMode.md)
  - Sets the mode for the reference voltage output to control the power supply's output voltage.

- [SerialSetOnErrorHandler](Functions/CAPLfunctionVTSSerialSetOnErrorHandler.md)
- [vtsSerialSetOnErrorHandler](Functions/CAPLfunctionVTSvtsSerialSetOnErrorHandler.md)
  - Sets the callback that notifies when an error occurred during a send or receive operation.

- [SerialSetOnReceiveHandler](Functions/CAPLfunctionVTSSerialSetOnReceiveHandler.md)
- [vtsSerialSetOnReceiveHandler](Functions/CAPLfunctionVTSvtsSerialSetOnReceiveHandler.md)
  - Sets the callback that notifies when data has been received on the serial port of the specified channel.

- [SerialSetOnSendHandler](Functions/CAPLfunctionVTSSerialSetOnSendHandler.md)
- [vtsSerialSetOnSendHandler](Functions/CAPLfunctionVTSvtsSerialSetOnSendHandler.md)
  - Sets the callback that notifies when a send operation on the serial port of the specified channel is completed successfully.

- [SetWFParams](Functions/CAPLfunctionVTSSetWFParams.md)
- [vtsSetWFParams](Functions/CAPLfunctionVTSvtsSetWFParams.md)
  - Configures the parameters for the output of a control voltage curve.

- [StartStimulation](Functions/CAPLfunctionVTSStartStimulation.md)
- [vtsStartStimulation](Functions/CAPLfunctionVTSvtsStartStimulation.md)
  - Starts stimulation output.

- [StopStimulation](Functions/CAPLfunctionVTSStopStimulation.md)
- [vtsStopStimulation](Functions/CAPLfunctionVTSvtsStopStimulation.md)
  - Stops stimulation output.

## VT8006/VT8012 related Functions [▲ back](#Shortcuts)

- [vtsSetBackplaneRelay](Functions/CAPLfunctionVTSvtsSetBackplaneRelay.md)
  - Closes/opens the auxiliary relay on a connected VT backplane.

[VT System](../../CANoeCANalyzer/VTSystem/VTSystem.md) • [Enumeration](CAPLfunctionsVTSystemEnumeration.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)