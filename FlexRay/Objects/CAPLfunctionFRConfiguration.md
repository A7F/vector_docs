[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Objects/CAPLfunctionFRConfiguration.md)

## frConfiguration

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frConfiguration

**Valid for**: CANoe DE

### Function Syntax

```
frConfiguration <configuration var>;
```

### Description

Can be used to create a FlexRay parameter object. The data content of this object is all protocol parameters relevant to FlexRay in the context of initializing a FlexRay Communication Controller. The object data can be manipulated or read out by selectors associated with this object.

Initially, all protocol parameters are set to a value of 0.

The [frGetConfiguration](../Functions/CAPLfunctionFRGetConfiguration.md) or [frSetConfiguration](../Functions/CAPLfunctionFRSetConfiguration.md) functions are used to read or set parameters from or in the FlexRay interface’s Communication Controller.

### Parameters

- **`<configuration var>`**: Character string defining the object's variable name.

### Selectors

- **FRBaudrate**: Baudrate in kBit/s.
- **gdMacrotick**: FlexRay protocol parameter. See FlexRay specification. Data type: double
- **gMacroPerCycle**: FlexRay protocol parameter. See FlexRay specification.
- **gdNIT**: FlexRay protocol parameter. See FlexRay specification.
- **gdSampleClockPeriod**: FlexRay protocol parameter. See FlexRay specification. Data type: double
- **gdTSSTransmitter**: FlexRay protocol parameter. See FlexRay specification.
- **gPayloadLengthStatic**: FlexRay protocol parameter. See FlexRay specification.
- **gdActionPointOffset**: FlexRay protocol parameter. See FlexRay specification.
- **gdStaticSlot**: FlexRay protocol parameter. See FlexRay specification.
- **gNumberOfStaticSlots**: FlexRay protocol parameter. See FlexRay specification.
- **gdMinislotActionPointOffset**: FlexRay protocol parameter. See FlexRay specification.
- **gdMinislot**: FlexRay protocol parameter. See FlexRay specification.
- **gNumberOfMinislots**: FlexRay protocol parameter. See FlexRay specification.
- **gClusterDriftDamping**: FlexRay protocol parameter. See FlexRay specification.
- **gListenNoise**: FlexRay protocol parameter. See FlexRay specification.
- **gColdstartAttempts**: FlexRay protocol parameter. See FlexRay specification.
- **gSyncNodeMay**: FlexRay protocol parameter. See FlexRay specification.
- **gOffsetCorrectionStart**: FlexRay protocol parameter. See FlexRay specification.
- **gdDynamicSlotIdlePhase**: FlexRay protocol parameter. See FlexRay specification.
- **gdSymbolWindow**: FlexRay protocol parameter. See FlexRay specification.
- **gdCASRxLowMax**: FlexRay protocol parameter. See FlexRay specification.
- **gdWakeupSymbolRxIdle**: FlexRay protocol parameter. See FlexRay specification.
- **gdWakeupSymbolRxLow**: FlexRay protocol parameter. See FlexRay specification.
- **gdWakeupSymbolRxWindow**: FlexRay protocol parameter. See FlexRay specification.
- **gdWakeupSymbolTxIdle**: FlexRay protocol parameter. See FlexRay specification.
- **gdWakeupSymbolTxLow**: FlexRay protocol parameter. See FlexRay specification.
- **gMaxWithoutClockCorrectionFatal**: FlexRay protocol parameter. See FlexRay specification.
- **gMaxWithoutClockCorrectionPassive**: FlexRay protocol parameter. See FlexRay specification.
- **gNetworkManagementVectorLength**: FlexRay protocol parameter. See FlexRay specification.
- **pChannels**: FlexRay protocol parameter. See FlexRay specification.
- **pMicroPerCycle**: FlexRay protocol parameter. See FlexRay specification.
- **pSamplesPerMicrotick**: FlexRay protocol parameter. See FlexRay specification.
- **pPayloadLengthDynMax**: FlexRay protocol parameter. See FlexRay specification.
- **pPayloadLengthFIFO**: Size of the maximum data length that can be received via the FIFO buffer in 16-bit words.
- **pLatestTx**: FlexRay protocol parameter. See FlexRay specification.
- **pdMaxDrift**: FlexRay protocol parameter. See FlexRay specification.
- **pdAcceptedStartupRange**: FlexRay protocol parameter. See FlexRay specification.
- **pClusterDriftDamping**: FlexRay protocol parameter. See FlexRay specification.
- **pDecodingCorrection**: FlexRay protocol parameter. See FlexRay specification.
- **pDelayCompensation_A**: FlexRay protocol parameter. See FlexRay specification.
- **pDelayCompensation_B**: FlexRay protocol parameter. See FlexRay specification.
- **pOffsetCorrectionOut**: FlexRay protocol parameter. See FlexRay specification.
- **pRateCorrectionOut**: FlexRay protocol parameter. See FlexRay specification.
- **pExternOffsetCorrection**: FlexRay protocol parameter. See FlexRay specification.
- **pExternRateCorrection**: FlexRay protocol parameter. See FlexRay specification.
- **pExternCorrectionMode**: Defines the addition mode for the external rate and offset correction values. Possible values are: 0, 5, 10, 11, 14 and 15.
- **pMacroInitialOffset_A**: FlexRay protocol parameter. See FlexRay specification.
- **pMacroInitialOffset_B**: FlexRay protocol parameter. See FlexRay specification.
- **pMicroInitialOffset_A**: FlexRay protocol parameter. See FlexRay specification.
- **pMicroInitialOffset_B**: FlexRay protocol parameter. See FlexRay specification.
- **pWakeupChannel**: FlexRay protocol parameter. See FlexRay specification.
- **pWakeupPattern**: FlexRay protocol parameter. See FlexRay specification.
- **pAllowHaltDueToClock**: FlexRay protocol parameter. See FlexRay specification.
- **pAllowPassiveToActive**: FlexRay protocol parameter. See FlexRay specification.
- **pBGTick**: FlexRay protocol parameter. See FlexRay specification.
- **pPhysicalLayer**: Defines the physical layer to be used.
- **pSingleSlotEnabled**: FlexRay protocol parameter. See FlexRay specification.
- **pBGEnable**: FlexRay protocol parameter. See FlexRay specification.
- **pDynamicSegmentEnable**: FlexRay protocol parameter. See FlexRay specification.
- **pChannelsMTS**: FlexRay protocol parameter. See FlexRay specification.
- **pCCVersion**: Indicates the selected FlexRay interface type. Write-protected!
- **pStrobePointPosition**: E-Ray parameter. See E-Ray specification.
- **pdMicrotick**: FlexRay protocol parameter. See FlexRay specification. Data type: double. In function [frSetConfiguration](../Functions/CAPLfunctionFRSetConfiguration.md) this parameter is ignored!

### Example

For an example see functions [frGetConfiguration](../Functions/CAPLfunctionFRGetConfiguration.md) and [frSetConfiguration](../Functions/CAPLfunctionFRSetConfiguration.md).

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
