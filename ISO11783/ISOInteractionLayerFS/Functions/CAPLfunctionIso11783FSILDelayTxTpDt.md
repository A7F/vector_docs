[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILDelayTxTpDt.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_DelayTxTpDt**

# FSIL_DelayTxTpDt

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long FSIL_DelayTxTpDt(long firstMsg, long numOfMsg, long timeout); //Form 1
long FSIL_DelayTxTpDt(dbNode node, long firstMsg, long numOfMsg, long timeout); //Form 2
```

## Description

Delays transmitting of (E)TP.DT messages generated and sent by the interaction layer. The messages to be delayed are identified by their occurrences on the bus, starting at 1 until the given message count is reached. The given range of DT messages are delayed every time until the CAPL function [FSIL_ResetDelayedTxTpDt](CAPLfunctionIso11783FSILResetDelayedTxTpDt.md) is called.

The delay time is added to the value set by [FSIL_SetNodeProperty("TPDTLatency", …)](CAPLfunctionIso11783FSILSetNodeProperty.md).

## Parameters

- **firstMsg**: Sequence number of the first DT message that shall be blocked [1…n].
- **numOfMsg**: Number of DT messages that shall be blocked [1…n].
- **timeout**: The delay in milliseconds to continue the transmission with regularly sent DT messages [1…3600000].
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3002**: Parameter **firstMsg** must be greater than 0
- **-3003**: Parameter **numOfMsg** must be greater than 0

## Example

```plaintext
on start {
  long res;
  // Delay TP.DT packets 6, 7, 8, 9 by 200 ms each. Continue with packet no. 10 without delay.
  res = FSIL_DelayTxTpDt(6, 4, 200);
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
