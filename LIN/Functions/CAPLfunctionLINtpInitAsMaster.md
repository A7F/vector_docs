[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINtpInitAsMaster.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » LINtp_InitAsMaster

# LINtp_InitAsMaster

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void LINtp_InitAsMaster();
```

## Description

Can only be called in `on prestart`.

Normally the LINtp implementation will detect whether it runs in the LIN master node automatically. But if the LINtp.DLL shall be able to send diagnostics request from a node that is not the master, e.g. a test module, this is not the case. The automatic detection would assume the slave role.

Calling this function in the `on prestart` phase will initialize the transport protocol in master role, i.e. sending of diagnostics requests on TP level is possible.

## Parameters

—

## Return Values

—

## Example

```plaintext
on preStart
{
  if( cIsTester)
    LINtp_InitAsMaster();
}
```
