[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDconnectenvvar.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783PDDConnectEnvVar

# Iso11783PDDConnectEnvVar

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDConnectEnvVar( dword ecuHandle, dbSignal signal, dword elementNumber, char envVarName[] );
long Iso11783PDDConnectEnvVar( dword ecuHandle, dword ddi, dword elementNumber, char envVarName[] );
```

## Description

The function connects a process variable with an environment variable.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must previously have been created with [Iso11783CreateeECU](CAPLfunctionIso11783CreateECU.md).
- **signal**: Signal from the database. The attribute [DDI](../../../../CANoeCANalyzer/ISO11783/processData/ProcessDataDefinition.md) must have been defined for the signal. The signal must be defined in the same database as the node!
- **ddi**: Data dictionary identifier, 0x0000..0xFFFF
- **elementNumber**: Element number, 0x000..0xFFF
- **envVarName**: Name of the environment variable

## Return Values

[Error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
if (Iso11783PDDLoadDeviceDescription( ecuHandle, "Sprayer.XML" ) == 0) {
  Iso11783PDDConnectEnvVar( ecuHandle, 0x0060, 1, "EvSprayer_TankVolume" );
  Iso11783PDDConnectEnvVar( ecuHandle, 0x0048, 2, "EvSprayer_AppRatePerArea" );
} else {
  write( "Error while load task file" );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)