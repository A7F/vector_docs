[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/FlexRay/Functions/CAPLfunctionFRGetConfiguration.md)

[CAPL Functions](../../CAPLfunctions.md) » [FlexRay](../CAPLfunctionsFlexrayOverview.md) » frGetConfiguration

# frGetConfiguration

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`frGetConfiguration( int channel, frConfiguration<configuration var> );`

## Description

This function copies the FlexRay protocol parameters to **`<configuration var>`**.

## Parameters

- **channel**: FlexRay channel (cluster number).
- **`<configuration var>`**: Name of the variable referenced by the configuration object. The variable name was defined when the object was created using [frConfiguration](../Objects/CAPLfunctionFRConfiguration.md).

## Return Values

—

## Example

The following CAPL function outputs all FlexRay protocol parameters in the Write Window.

```plaintext
variables
{
   frConfiguration gFRParams;
}

void printFRConf ()
{
   frGetConfiguration(%CHANNEL%, gFRParams);
   Write("%33s = %6d %s", "pCCVersion", gFRParams.pCCVersion, "");
   Write("%33s = %6ld %s","FRBaudrate", gFRParams.FRBaudrate, "kBit/s");
   Write("%33s = %6f %s", "gdMacrotick", gFRParams.gdMacrotick, "us");
   Write("%33s = %6d %s", "gMacroPerCycle", gFRParams.gMacroPerCycle, "MT");
   Write("%33s = %6d %s", "gdNIT", gFRParams.gdNIT, "MT");
   Write("%33s = %6f %s", "gdSampleClockPeriod", gFRParams.gdSampleClockPeriod, "us");
   Write("%33s = %6d %s", "gdTSSTransmitter", gFRParams.gdTSSTransmitter, "Bit");
   Write("%33s = %6d %s", "gPayloadLengthStatic", gFRParams.gPayloadLengthStatic, "Words");
   Write("%33s = %6d %s", "gdActionPointOffset", gFRParams.gdActionPointOffset, "MT");
   Write("%33s = %6d %s", "gdStaticSlot", gFRParams.gdStaticSlot, "MT");
   Write("%33s = %6d %s", "gNumberOfStaticSlots", gFRParams.gNumberOfStaticSlots, "#");
   Write("%33s = %6d %s", "gdMinislotActionPointOffset", gFRParams.gdMinislotActionPointOffset, "MT");
   Write("%33s = %6d %s", "gdMinislot", gFRParams.gdMinislot, "MT");
   Write("%33s = %6d %s", "gNumberOfMinislots", gFRParams.gNumberOfMinislots, "#");
   Write("%33s = %6d %s", "gClusterDriftDamping", gFRParams.gClusterDriftDamping, "");
   Write("%33s = %6d %s", "gListenNoise", gFRParams.gListenNoise, "");
   Write("%33s = %6d %s", "gColdStartAttempts", gFRParams.gColdStartAttempts, "#");
   Write("%33s = %6d %s", "gSyncNodeMax", gFRParams.gSyncNodeMax, "#");
   Write("%33s = %6d %s", "gOffsetCorrectionStart", gFRParams.gOffsetCorrectionStart, "MT");
   Write("%33s = %6d %s", "gdDynamicSlotIdlePhase", gFRParams.gdDynamicSlotIdlePhase, "MS");
   Write("%33s = %6d %s", "gdSymbolWindow", gFRParams.gdSymbolWindow, "MT");
   Write("%33s = %6d %s", "gdCASRxLowMax", gFRParams.gdCASRxLowMax, "Bit");
   Write("%33s = %6d %s", "gdCASRxLowMin", gFRParams.gdCASRxLowMin, "Bit");
   Write("%33s = %6d %s", "gdWakeupSymbolRxIdle", gFRParams.gdWakeupSymbolRxIdle, "Bit");
   Write("%33s = %6d %s", "gdWakeupSymbolRxLow", gFRParams.gdWakeupSymbolRxLow, "Bit");
   Write("%33s = %6d %s", "gdWakeupSymbolRxWindow", gFRParams.gdWakeupSymbolRxWindow, "Bit");
   Write("%33s = %6d %s", "gdWakeupSymbolTxIdle", gFRParams.gdWakeupSymbolTxIdle, "Bit");
   Write("%33s = %6d %s", "gdWakeupSymbolTxLow", gFRParams.gdWakeupSymbolTxLow, "Bit");
   Write("%33s = %6d %s", "gMaxWithoutClockCorrectionFatal", gFRParams.gMaxWithoutClockCorrectionFatal, "double cycles");
   Write("%33s = %6d %s", "gMaxWithoutClockCorrectionPassive", gFRParams.gMaxWithoutClockCorrectionPassive, "double cycles");
   Write("%33s = %6d %s", "gNetworkManagementVectorLength", gFRParams.gNetworkManagementVectorLength, "Bytes");
   Write("%33s = %6d %s", "pChannels", gFRParams.pChannels, "");
   Write("%33s = %6d %s", "pMicroPerCycle", gFRParams.pMicroPerCycle, "uT");
   Write("%33s = %6d %s", "pSamplesPerMicrotick", gFRParams.pSamplesPerMicrotick, "#");
   Write("%33s = %6d %s", "pPayloadLengthDynMax", gFRParams.pPayloadLengthDynMax, "Words");
   Write("%33s = %6d %s", "pPayloadLengthFIFO", gFRParams.pPayloadLengthFIFO, "Words");
   Write("%33s = %6d %s", "pLatestTx", gFRParams.pLatestTx, "MS");
   Write("%33s = %6d %s", "pdMaxDrift", gFRParams.pdMaxDrift, "uT");
   Write("%33s = %6d %s", "pdAcceptedStartupRange", gFRParams.pdAcceptedStartupRange, "uT");
   Write("%33s = %6d %s", "pdListenTimeout", gFRParams.pdListenTimeout, "uT");
   Write("%33s = %6d %s", "pClusterDriftDamping", gFRParams.pClusterDriftDamping, "uT");
   Write("%33s = %6d %s", "pDecodingCorrection", gFRParams.pDecodingCorrection, "uT");
   Write("%33s = %6d %s", "pDelayCompensation_A", gFRParams.pDelayCompensation_A, "uT");
   Write("%33s = %6d %s", "pDelayCompensation_B", gFRParams.pDelayCompensation_B, "uT");
   Write("%33s = %6d %s", "pOffsetCorrectionOut", gFRParams.pOffsetCorrectionOut, "uT");
   Write("%33s = %6d %s", "pRateCorrectionOut", gFRParams.pRateCorrectionOut, "uT");
   Write("%33s = %6d %s", "pExternOffsetCorrection", gFRParams.pExternOffsetCorrection, "uT");
   Write("%33s = %6d %s", "pExternRateCorrection", gFRParams.pExternRateCorrection, "uT");
   Write("%33s = %6d %s", "pExternCorrectionMode", gFRParams.pExternCorrectionMode, "");
   Write("%33s = %6d %s", "pMacroInitialOffset_A", gFRParams.pMacroInitialOffset_A, "MT");
   Write("%33s = %6d %s", "pMacroInitialOffset_B", gFRParams.pMacroInitialOffset_B, "MT");
   Write("%33s = %6d %s", "pMicroInitialOffset_A", gFRParams.pMicroInitialOffset_A, "uT");
   Write("%33s = %6d %s", "pMicroInitialOffset_B", gFRParams.pMicroInitialOffset_B, "uT");
   Write("%33s = %6d %s", "pWakeupChannel", gFRParams.pWakeupChannel, "");
   Write("%33s = %6d %s", "pWakeupPattern", gFRParams.pWakeupPattern, "#");
   Write("%33s = %6d %s", "pAllowHaltDueToClock", gFRParams.pAllowHaltDueToClock, "Boolean");
   Write("%33s = %6d %s", "pAllowPassiveToActive", gFRParams.pAllowPassiveToActive, "cycles");
   Write("%33s = %6d %s", "pBGTick", gFRParams.pBGTick, "Boolean");
   Write("%33s = %6d %s", "pPhysicalLayer", gFRParams.pPhysicalLayer, "");
   Write("%33s = %6d %s", "pSingleSlotEnabled", gFRParams.pSingleSlotEnabled, "Boolean");
   Write("%33s = %6d %s", "pBGEnable", gFRParams.pBGEnable, "Boolean");
   Write("%33s = %6d %s", "pDynamicSegmentEnable", gFRParams.pDynamicSegmentEnable, "Boolean");
   Write("%33s = %6d %s", "pStrobePointPosition", gFRParams.pStrobePointPosition, "");
   Write("%33s = %6f %s", "pdMicrotick", gFRParams.pdMicrotick, "us");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)