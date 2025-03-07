[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/CAPLfunctionsVTSystemEnumeration.md)

**CAPL Functions** » **VT System** » Enumeration

# Enumeration

**Valid for**: CANoe DE • CANoe:lite DE

### eVTSLoadMode

- **Value**: 0
  - **Enum**: eVTSLoadModeInactive
  - **Short Description**: Internal load not active
- **Value**: 1
  - **Enum**: eVTSLoadModeCurrentControl
  - **Short Description**: Current control
- **Value**: 2
  - **Enum**: eVTSLoadModeResistanceControl
  - **Short Description**: Resistance control

## eVTSMeasurementMode

- **Value**: 0
  - **Enum**: eVTSMeasurementModeDirect
  - **Short Description**: Differential voltage, unfiltered
- **Value**: 1
  - **Enum**: eVTSMeasurementModeFiltered
  - **Short Description**: Differential voltage, 10 kHz filter active
- **Value**: 2
  - **Enum**: eVTSMeasurementModeLineAToGnd
  - **Short Description**: Voltage line A to ground
- **Value**: 3
  - **Enum**: eVTSMeasurementModeLineBToGnd
  - **Short Description**: Voltage line B to ground

## eVTSImpedanceMode

- **Value**: 0
  - **Enum**: eVTSImpedanceModeHigh
  - **Short Description**: High impedance (default state)
- **Value**: 1
  - **Enum**: eVTSImpedanceModeLow
  - **Short Description**: Low impedance (advantageous for measurement of PWM frequency and duty cycle)

## eVTSTrigger

- **Value**: 1
  - **Enum**: eVTSTrigger1
  - **Short Description**: Trigger 1
- **Value**: 2
  - **Enum**: eVTSTrigger2
  - **Short Description**: Trigger 2
- **Value**: 3
  - **Enum**: eVTSTrigger3
  - **Short Description**: Trigger 3
- **Value**: 4
  - **Enum**: eVTSTrigger4
  - **Short Description**: Trigger 4
- **Value**: 5
  - **Enum**: eVTSTrigger5
  - **Short Description**: Trigger 5
- **Value**: 6
  - **Enum**: eVTSTrigger6
  - **Short Description**: Trigger 6
- **Value**: 7
  - **Enum**: eVTSTrigger7
  - **Short Description**: Trigger 7
- **Value**: 8
  - **Enum**: eVTSTrigger8
  - **Short Description**: Trigger 8

## eVTSTriggerSourceChannel

- **Value**: 0
  - **Enum**: eVTSTriggerSourceChannelInactive
  - **Short Description**: Source Channel inactive
- **Value**: 1
  - **Enum**: eVTSTriggerSourceChannel1
  - **Short Description**: Source Channel 1
- **Value**: 2
  - **Enum**: eVTSTriggerSourceChannel2
  - **Short Description**: Source Channel 2
- **Value**: 3
  - **Enum**: eVTSTriggerSourceChannel3
  - **Short Description**: Source Channel 3
- **Value**: 4
  - **Enum**: eVTSTriggerSourceChannel4
  - **Short Description**: Source Channel 4

## eVTSTriggerEdgeType

- **Value**: 0
  - **Enum**: eVTSTriggerEdgeTypeRising
  - **Short Description**: Edge Mode: Trigger detects only rising edges
- **Value**: 1
  - **Enum**: eVTSTriggerEdgeTypeFalling
  - **Short Description**: Edge Mode: Trigger detects only falling edges

## eVTSTriggerType

- **Value**: 0
  - **Enum**: eVTSTriggerTypeEdge
  - **Short Description**: Edge
- **Value**: 1
  - **Enum**: eVTSTriggerTypeLevel
  - **Short Description**: Level

## eVTSCurveType

- **Value**: 0
  - **Enum**: eVTSCurveTypeConstant
  - **Short Description**: Constant value, determined by the corresponding output system variable.
- **Value**: 1
  - **Enum**: eVTSCurveTypePWM
  - **Short Description**: PWM
- **Value**: 2
  - **Enum**: eVTSCurveTypeAnalogWaveform
  - **Short Description**: Analog wave form; loaded using [LoadWFVoltage](Functions/CAPLfunctionVTSLoadWFVoltage.md)
- **Value**: 3
  - **Enum**: eVTSCurveTypeBitStream
  - **Short Description**: Bitstream (= digital wave form); loaded using [LoadWFBitStream](Functions/CAPLfunctionVTSLoadWFBitStream.md)
- **Value**: 4
  - **Enum**: eVTSCurveTypeUserFPGA
  - **Short Description**: User FPGA. If the output of a module shall be controlled by a user-programmable FPGA this type has to be set.

## eVTSStimulationMode

- **Value**: 0
  - **Enum**: eVTSStimulationModeNone
  - **Short Description**: Internal stimulation not active
- **Value**: 1
  - **Enum**: eVTSStimulationModeVoltage
  - **Short Description**: Voltage stimulation
- **Value**: 2
  - **Enum**: eVTSStimulationModePotentiometer
  - **Short Description**: Potentiometer stimulation (VT2004 only)
- **Value**: 3
  - **Enum**: eVTSStimulationModeResistanceGreater
  - **Short Description**: Resistance stimulation R> (on switching between resistance values, only intermediate states with resistance values higher than the output or target resistance will occur) (VT2004 only)
- **Value**: 4
  - **Enum**: eVTSStimulationModeResistanceLower
  - **Short Description**: Resistance stimulation R< (on switching between resistance values, only intermediate states with lower resistance values will occur) (VT2004 only)

## eVTS2816MeasurementMode

- **Value**: 0
  - **Enum**: eVTS2816MeasurementModeVoltageDifferential60V
  - **Short Description**: Differential voltage, range ±60V
- **Value**: 1
  - **Enum**: eVTS2816MeasurementModeVoltageDifferential10V
  - **Short Description**: Differential voltage, range ±10V
- **Value**: 2
  - **Enum**: eVTS2816MeasurementModeVoltageLineAToGnd60V
  - **Short Description**: Voltage line A to ground (single-ended), range ±60V
- **Value**: 3
  - **Enum**: eVTS2816MeasurementModeVoltageLineAToGnd10V
  - **Short Description**: Voltage line A to ground (single-ended), range ±10V
- **Value**: 4
  - **Enum**: eVTS2816MeasurementModeCurrent
  - **Short Description**: Current, range ±5A

## eVTSOutputRange

- **Value**: 0
  - **Enum**: eVTSOutputRangeZeroTo28V
  - **Short Description**: 0…28V
- **Value**: 1
  - **Enum**: eVTSOutputRangePlusMinus10V
  - **Short Description**: -10V…+10V

## eVTSOutputSourceGroup

- **Value**: 0
  - **Enum**: eVTSOutputSourceGroupChannels1To4
  - **Short Description**: Channels 1–4
- **Value**: 1
  - **Enum**: eVTSOutputSourceGroupChannels5To8
  - **Short Description**: Channels 5–8
- **Value**: 2
  - **Enum**: eVTSOutputSourceGroupChannels9To12
  - **Short Description**: Channels 9–12
- **Value**: 3
  - **Enum**: eVTSOutputSourceGroupChannels13To16
  - **Short Description**: Channels 13–16
- **Value**: 4
  - **Enum**: eVTSOutputSourceGroupChannels17To20
  - **Short Description**: Channels 17–20
- **Value**: 5
  - **Enum**: eVTSOutputSourceGroupChannels21To24
  - **Short Description**: Channels 21-24
- **Value**: 6
  - **Enum**: eVTSOutputSourceGroupChannels25To28
  - **Short Description**: Channels 25-28
- **Value**: 7
  - **Enum**: eVTSOutputSourceGroupChannels29To32
  - **Short Description**: Channels 29-32
- **Value**: 8
  - **Enum**: eVTSOutputSourceGroupChannels33To36
  - **Short Description**: Channels 33-36
- **Value**: 9
  - **Enum**: eVTSOutputSourceGroupChannels37To40
  - **Short Description**: Channels 37-40
- **Value**: 10
  - **Enum**: eVTSOutputSourceGroupChannels41To44
  - **Short Description**: Channels 41-44
- **Value**: 11
  - **Enum**: eVTSOutputSourceGroupChannels45To48
  - **Short Description**: Channels 45-48

## eVTSOutputSource

- **Value**: 0
  - **Enum**: eVTSOutputSourceVExt
  - **Short Description**: Vext
- **Value**: 1
  - **Enum**: eVTSOutputSourceVBat
  - **Short Description**: Vbatt

## eVTS2848OutputMode

- **Value**: 0
  - **Enum**: eVTS2848OutputModeInactive
  - **Short Description**: Output off
- **Value**: 1
  - **Enum**: eVTS2848OutputModeHighsideSwitch
  - **Short Description**: High side switch
- **Value**: 2
  - **Enum**: eVTS2848OutputModeLowsideSwitch
  - **Short Description**: Low side switch
- **Value**: 3
  - **Enum**: eVTS2848OutputModePushPull
  - **Short Description**: Push pull

## eVTSThresholdGroup

- **Value**: 0
  - **Enum**: eVTSThresholdGroupChannels1To8
  - **Short Description**: Channels 1–8
- **Value**: 1
  - **Enum**: eVTSThresholdGroupChannels9To16
  - **Short Description**: Channels 9–16
- **Value**: 2
  - **Enum**: eVTSThresholdGroupChannels17To24
  - **Short Description**: Channels 17–24
- **Value**: 3
  - **Enum**: eVTSThresholdGroupChannels25To32
  - **Short Description**: Channels 25–32
- **Value**: 4
  - **Enum**: eVTSThresholdGroupChannels33To40
  - **Short Description**: Channels 33–40
- **Value**: 5
  - **Enum**: eVTSThresholdGroupChannels41To48
  - **Short Description**: Channels 41–48

## eVTSOutputMode

- **Value**: 0
  - **Enum**: eVTSOutputModeInactive
  - **Short Description**: inactive
- **Value**: 1
  - **Enum**: eVTSOutputModeActive
  - **Short Description**: output active
- **Value**: -1
  - **Enum**: eVTSOutputModeShortCircuit
  - **Short Description**: short circuit

## eVTSBaudRate

- **Value**: 1200
  - **Enum**: eVTSBaudRate1200
  - **Short Description**: The symbol rate to use for reception and transmission 1200 baud
- **Value**: 2400
  - **Enum**: eVTSBaudRate2400
  - **Short Description**: The symbol rate to use for reception and transmission 2400 baud
- **Value**: 4800
  - **Enum**: eVTSBaudRate4800
  - **Short Description**: The symbol rate to use for reception and transmission 4800 baud
- **Value**: 9600
  - **Enum**: eVTSBaudRate9600
  - **Short Description**: The symbol rate to use for reception and transmission 9600 baud
- **Value**: 19200
  - **Enum**: eVTSBaudRate19200
  - **Short Description**: The symbol rate to use for reception and transmission 19200 baud
- **Value**: 38400
  - **Enum**: eVTSBaudRate38400
  - **Short Description**: The symbol rate to use for reception and transmission 38400 baud

## eVTSParity

- **Value**: 0
  - **Enum**: eVTSParityNone
  - **Short Description**: no parity used, i.e. frame contains no parity bit
- **Value**: 1
  - **Enum**: eVTSParityOdd
  - **Short Description**: odd parity
- **Value**: 2
  - **Enum**: eVTSParityEven
  - **Short Description**: even parity

## eVTSDataBits

- **Value**: 7
  - **Enum**: eVTSDataBitsSeven
  - **Short Description**: 7 Data Bits
- **Value**: 8
  - **Enum**: eVTSDataBitsEight
  - **Short Description**: 8 Data Bits

## eVTSStopBits

- **Value**: 1
  - **Enum**: eVTSStopBitsOne
  - **Short Description**: 1 StopBit
- **Value**: 2
  - **Enum**: eVTSStopBitsTwo
  - **Short Description**: 2 StopBits

## eVTSInterconnectionMode

- **Value**: 0
  - **Enum**: eVTSInterconnectionModeSupInt
  - **Short Description**: Internal Power Supply only (mode supint)
- **Value**: 1
  - **Enum**: eVTSInterconnectionModeSup1
  - **Short Description**: Power Supply 1 only (mode sup1)
- **Value**: 2
  - **Enum**: eVTSInterconnectionModeSup2
  - **Short Description**: Power Supply 2 only (mode sup2)
- **Value**: 3
  - **Enum**: eVTSInterconnectionModeSupIntSup1
  - **Short Description**: Two independent power supplies for OUT1 and OUT2: internal power supply and power supply 1 (mode supint_sup1)
- **Value**: 4
  - **Enum**: eVTSInterconnectionModeSupIntSup2
  - **Short Description**: Two independent power supplies for OUT1 and OUT2: internal power supply and power supply 2 (mode supint_sup2)
- **Value**: 5
  - **Enum**: eVTSInterconnectionModeSup1SupInt
  - **Short Description**: Two independent power supplies for OUT1 and OUT2: power supply 1 and internal power supply (mode sup1_supint)
- **Value**: 6
  - **Enum**: eVTSInterconnectionModeSup1Sup2
  - **Short Description**: Two independent power supplies for OUT1 and OUT2: power supply 1 and power supply 2 (mode sup1_sup2)
- **Value**: 7
  - **Enum**: eVTSInterconnectionModeSup2SupInt
  - **Short Description**: Two independent power supplies for OUT1 and OUT2: power supply 2 and internal power supply (mode sup2_supint)
- **Value**: 8
  - **Enum**: eVTSInterconnectionModeSup2Sup1
  - **Short Description**: Two independent power supplies for OUT1 and OUT2: power supply 2 and power supply 1 (mode sup2_sup1)
- **Value**: 9
  - **Enum**: eVTSInterconnectionModeSupSeries
  - **Short Description**: Power supply 1 and power supply 2 are connected in series (sup_series)
- **Value**: 10
  - **Enum**: eVTSInterconnectionModeSupParallel
  - **Short Description**: Power supply 1 and power supply 2 are connected parallel (sup_parallel)

## eVTSMaxCurrentMode

- **Value**: 0
  - **Enum**: eVTSMaxCurrentModeInactive
  - **Short Description**: Max current control voltage output not active
- **Value**: 1
  - **Enum**: eVTSMaxCurrentModeConstant
  - **Short Description**: Constant value, determined by the corresponding output system variable

## eVTSCurrentMeasurementRange

- **Value**: 0
  - **Enum**: eVTSCurrentMeasurementRange100uA
  - **Short Description**: All measuring ranges will be used.
- **Value**: 1
  - **Enum**: eVTSCurrentMeasurementRange1mA
  - **Short Description**: Lowermost used range: 100µA…1mA
- **Value**: 2
  - **Enum**: eVTSCurrentMeasurementRange10mA
  - **Short Description**: Lowermost used range: 1mA…10mA
- **Value**: 3
  - **Enum**: eVTSCurrentMeasurementRange100mA
  - **Short Description**: Lowermost used range: 10mA…100mA
- **Value**: 4
  - **Enum**: eVTSCurrentMeasurementRange1A
  - **Short Description**: Lowermost used range: 100mA…1A
- **Value**: 5
  - **Enum**: eVTSCurrentMeasurementRange10A
  - **Short Description**: Lowermost used range: 1A…10A
- **Value**: 6
  - **Enum**: eVTSCurrentMeasurementRange100A
  - **Short Description**: Lowermost used range: 10A…100A

## eVTS2808CurrentMeasurementRange

- **Value**: 0
  - **Enum**: eVTS2808CurrentMeasurementRange50mA
  - **Short Description**: All measuring ranges will be used
- **Value**: 1
  - **Enum**: eVTS2808CurrentMeasurementRange1A
  - **Short Description**: Lowermost used range: 50mA…1A
- **Value**: 2
  - **Enum**: eVTS2808CurrentMeasurementRange20A
  - **Short Description**: Lowermost used range: 1A…20A

## eVTSRefVoltageMode

- **Value**: 0
  - **Enum**: eVTSRefVoltageModeInactive
  - **Short Description**: Reference voltage output not active
- **Value**: 1
  - **Enum**: eVTSRefVoltageModeConstant
  - **Short Description**: Constant value, determined by the corresponding output system variable
- **Value**: 2
  - **Enum**: eVTSRefVoltageModeAnalogWaveForm
  - **Short Description**: Analog wave form; loaded using LoadWFVoltage, then started using StartStimulation

## eVTSSerialErrors

- **Value**: 1
  - **Enum**: eVTSSerialErrorsSendOperationFailed
  - **Short Description**: Send operation failed
- **Value**: 2
  - **Enum**: eVTSSerialErrorsReceiveOperationFailed
  - **Short Description**: Receive operation failed
- **Value**: 4
  - **Enum**: eVTSSerialErrorsFrameError
  - **Short Description**: Frame error. May be caused by parity mismatch or any other frame mismatch (e.g. number of stop bits)
- **Value**: 8
  - **Enum**: eVTSSerialErrorsFrameParityError
  - **Short Description**: Frame parity error. Is caused by parity mismatch
- **Value**: 16
  - **Enum**: eVTSSerialErrorsBufferOverrun
  - **Short Description**: Buffer overrun. It is not specified if the driver of the sender cannot send fast enough, if it is up to the receiver which got too much data in too short time or anything else
- **Value**: 32
  - **Enum**: eVTSSerialErrorsBufferOverrunReceiver
  - **Short Description**: Buffer overrun at receiver
- **Value**: 64
  - **Enum**: eVTSSerialErrorsBreakState
  - **Short Description**: Break state. Other end requested to pause
- **Value**: 128
  - **Enum**: eVTSSerialErrorsTimeout
  - **Short Description**: Timeout. May be caused by wrongly set too short timeout

[Working with Symbolic Identifiers](../../Shared/CAPL/General/SymbolicIdentifiers.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)