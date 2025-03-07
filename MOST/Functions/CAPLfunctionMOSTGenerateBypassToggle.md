[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGenerateBypassToggle.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGenerateBypassToggle

# mostGenerateBypassToggle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Note

This functionality is only available for:

- VN2640
- OptoLyzer G2 3150o (At least firmware version V1.5.3 is required)

## Function Syntax

```plaintext
long mostGenerateBypassToggle(long channel, long invistime, long vistime, long repeat);
```

## Description

Starts (repeat > 0) or stops (repeat = 0) generation of Bypass-open-close transitions.

**VN2640:**

The bypass of the INIC used for simulation and stimulation is toggled. The node has to be in slave mode. The range for timing values is 10…65535 ms.

**OptoLyzer:**

The bypass of the additional stress network interface controller (NIC) in the OptoLyzer G2 3150o is switched. The bypass of the main NIC (which is responsible for sending and receiving) is not affected.

The stress network interface controller (NIC) must have **active bypass** or **bypass opened** (see [mostSetStressNodeParameter](CAPLfunctionMOSTSetGetStressNodeParameter.md)).

## Parameters

- **channel**: Channel of the connected interface
- **invistime**: Time during which node has its bypass closed (in ms)
- **vistime**: Time with opened bypass (in ms)
- **repeat**: 
  - 0: Stop stress
  - >0: Number of transitions
  - 0xFFFF: Generate transitions continually

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

```plaintext
// prepare stress NIC: set "active" bypass
mostSetStressNodeParameter(1, 3, 2);
// make the stress NIC visible two times for 50 ms each
mostGenerateBypassToggle(1, 100, 50, 2);
```

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [OnMostStress](../EventProcedures/CAPLfunctionOnMOSTStress.md) • [OnMostMPR](../EventProcedures/CAPLfunctionOnMOSTMPR.md) • [mostGenerateLockError](CAPLfunctionMOSTGenerateLockError.md) • [mostSetAllBypass](CAPLfunctionMOSTSetAllBypass.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)