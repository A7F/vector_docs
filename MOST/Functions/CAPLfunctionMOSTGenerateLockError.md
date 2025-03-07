[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGenerateLockError.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGenerateLockError

# mostGenerateLockError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This functionality is only available for VN2600/VN2610/VN2640 hardware, OptoLyzerOL3150o (firmware version >= V1.5.3) and OptoLyzerOL3050e (firmware version >= V1.5).

## Function Syntax

```plaintext
long mostGenerateLockError(long channel, long unmodtime, 
long modtime, long repeat);
```

## Description

Starts (repeat > 0) or stops (repeat = 0) generation of Light Unmodulated-Modulated transitions.

For OptoLyzerOL3150o: The stress network interface controller (NIC) must have its bypass opened (see [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md)).

## Parameters

- **channel**: Channel of the connected interface.
- **unmodtime**: Time during which unmodulated light is emitted (in ms).
- **modtime**: Time during which modulated light is emitted (in ms).
- **repeat**:
  - `0`: Stops the generation of Unmodulated-Modulated transitions
  - `>0`: Number of transitions
  - `0xFFFF`: Generate Unmodulated-Modulated transitions continually

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostGenerateBusloadAsync](CAPLfunctionMOSTGenerateBusloadAsync.md) • [mostGenerateBusloadCtrl](CAPLfunctionMOSTGenerateBusloadCtrl.md) • [mostGenerateLightError](CAPLfunctionMOSTGenerateLightError.md) • [OnMostStress](../EventProcedures/CAPLfunctionOnMOSTStress.md) | [mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [on mostLightLockError](../EventProcedures/CAPLfunctionOnMOSTLightLockError.md) • [mostGenerateBypassToggle](CAPLfunctionMOSTGenerateBypassToggle.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)