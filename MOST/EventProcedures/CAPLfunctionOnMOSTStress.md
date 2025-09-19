[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTStress.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostStress

# OnMostStress

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`OnMostStress(long mode, long state);`

## Description

The event procedure `OnMostStress()` will be called before the beginning and after the end of the stress generation.

## Parameters

- **mode**
  - 1: Stress generation with [mostGenerateLightError](../Functions/CAPLfunctionMOSTGenerateLightError.md)
  - 2: Stress generation with [mostGenerateLockError](../Functions/CAPLfunctionMOSTGenerateLockError.md)
  - 3: Stress generation with [mostGenerateBusloadCtrl](../Functions/CAPLfunctionMOSTGenerateBusloadCtrl.md)
  - 4: Stress generation with [mostGenerateBusloadAsync](../Functions/CAPLfunctionMOSTGenerateBusloadAsync.md)
  - 5: Stress generation with [mostSetRxBufferCtrl](../Functions/CAPLfunctionMOSTSetRxBufferCtrl.md)
  - 6: Stress generation with [mostSetTxLightPower](../Functions/CAPLfunctionMOSTSetTxLightPower.md)
  - 7: [mostGenerateBypassToggle](../Functions/CAPLfunctionMOSTGenerateBypassToggle.md)
  - 8: [mostSetSystemLockFlagUsage](../Functions/CAPLfunctionMOSTSetGetSystemLockFlagUsage.md)
  - 9: [mostSetShutDownFlagUsage](../Functions/CAPLfunctionMOSTSetGetShutDownFlagUsage.md)
  - 10: [mostGenerateBusloadEthPkt](../Functions/CAPLfunctionMOSTGenerateBusloadEthPkt.md)
  - 11: [mostSetRxBufferAsync](../Functions/CAPLfunctionMOSTSetRxBufferAsync.md)

- **state**
  - 0: Stress mode is stopped
    - Note:
      - mode = 5: Rx buffer enabled
      - mode = 6: normal light intensity
  - 1: Stress mode is started
    - Note:
      - mode = 5: Rx buffer disabled
      - mode = 6: 3db attenuation

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
