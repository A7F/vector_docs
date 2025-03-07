[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPIdentificationRequest.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_IdentificationRequest

# _DoIP_IdentificationRequest

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
long _DoIP_IdentificationRequest(long type, BYTE VINorEID[]);
```

## Description

A vehicle simulation has received a Vehicle Identification Request Message. The value returned will determine the reaction of the DoIP.DLL.

Note that requests not targeted at the ECU will be ignored.

## Parameters

- **type**
  - 1: No argument, VINorEID is empty
  - 2: Argument contains the EID (6 byte)
  - 3: Argument contains the VIN (17 byte/characters)

- **VINorEID**
  - The argument from the request message.

## Return Values

- **-2**
  - Ignore Vehicle Identification Request, i.e. do nothing

- **-1**
  - Send a **vehicle identification response** message after A_DoIP_Announce_Wait ms (default: 500 ms, can be configured in DoIP.INI)

- **≥ 0**
  - Send a **vehicle identification response** message after this many ms

## Example

```plaintext
long _DoIP_IdentificationRequest(long type, BYTE VINorEID[])
{
  if( type == 1)
    write( "Received VIR without argument");
  else if( type == 2)
    write( "Received VIR with EID: %02x:%02x:%02x:%02x:%02x:%02x"
    , VINorEID[0], VINorEID[1], VINorEID[2]
    , VINorEID[3], VINorEID[4], VINorEID[5]);
  else if( type == 3)
  {
    char textVIN[17];
    int i;
    for( i = 0; i < elcount(VINorEID); ++i)
      textVIN[i] = VINorEID[i];
    write( "Received VIR with VIN: %s", textVIN);
  }
  // The response message shall be sent after waiting between 100 and 500 ms
  return 100 + random(400);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)