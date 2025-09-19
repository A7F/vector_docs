[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsFiEnable.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAsFiEnable

# mostAsFiEnable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostAsFiEnable(long mode);
```

## Description

This function allows to temporarily switch the Application Socket Fault Injection on and off.

**Note:** To allow Fault Injection in general, the main switch in the **Network Hardware Configuration** dialog has to be activated for the corresponding channel.

The Application Socket Fault Injection allows modifications of the behavior of CANoe’s Application Socket services.

All AMS Tx messages from any Application Socket service will be passed through [OnMostFiAmsPreSend](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreSend.md) before sending. All AMS Rx messages to any Application Socket service will be passed through [OnMostFiAmsPreReceive](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreReceive.md) before receiving. Incoming and outgoing messages can be blocked or modified within these callbacks in order to simulate an imperfect device.

## Parameters

- **onoff**
  - 0: disable
  - 1: enable

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—
