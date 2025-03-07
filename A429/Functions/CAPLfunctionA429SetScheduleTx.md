[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/Functions/CAPLfunctionA429SetScheduleTx.md)

**CAPL Functions** » [A429](../CAPLfunctionsA429Overview.md) » a429SetScheduleTx

# a429SetScheduleTx

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword a429SetScheduleTx( a429word myA429word, dword myCycle );
```

## Description

Prepare an ARINC word to be transmitted cyclically by means of the hardware scheduling support. Calling this function modifies the [selectors](../CAPLfunctionsA429Selectors.md) **TxCycle** and **TxCtrl**.

**Note:** This modifies the ARINC word attributes only. For transmission call the function [output](CAPLfunctionA429output.md).

## Parameters

- **myA429word**: ARINC word
- **myCycle**: cycle time with microseconds resolution; value range [0 .. 600,000,000 (600 s)]; with 0 the behavior is switched to ON_REQ (see selector [TxCtrl](../CAPLfunctionsA429Selectors.md)).

## Return Values

- **0**: could not adapt cycle time; this happens, if
  - myCycle > 600,000,000
  - myCycle < ((32/Bitrate channel) + Gap time)
- **1**: cycle time was successfully adapted

## Example

—

[See Also](javascript:void(0);)