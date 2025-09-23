## SCC_SLAC_SetPSD

### Function Syntax

```c
SCC_SLAC_SetPSD ( byte PSD[] )
```

### Description
Fills the power spectral density map as a prerequisite for Amplitude Map Exchange. The data format is equal to the message CM_SLAC_AmpMap.Req, so the data will be sent exactly as set with this function.

To deactivate Amplitude Map Exchange (default), set a map of {0..0}.

To activate Amplitude Map Exchange, set a map that contains values != 0.

**Note**: Because the PSD is defined in values of 4 bit, only the lower half of each byte is considered.

### Parameters
- **PSD**: The Power Spectral Density in differences to the specified mean value and in [-dBm/Hz]. This must be a 58 or 917 byte array, depending on the setting in the XML configuration (see help pages [Configuration of Vehicle SCC Nodes (Smart Charging)](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCCConfigurationVehicleSCCNodes.md) and [Configuration of Charge Point SCC Nodes (Smart Charging)](../../../CANoeCANalyzer/SmartCharging/SCProcedures/SCConfigurationChargePointSCCNodes.md)).

### Return Values
- **0**: Not successful
- **1**: Successful

### Example
-