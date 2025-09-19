[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/KLine/Functions/CAPLfunctionDiagInitEcuSimulation.md)

**CAPL Functions** » [K-Line](../CAPLfunctionsKLineOverview.md) » DiagInitEcuSimulation

# DiagInitEcuSimulation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long DiagInitEcuSimulation(char ecuQualifier[])
```

## Description

Initialize CAPL node to represent a diagnostics ECU simulation. From now on the ECU can interpret and use all diagnostic objects in the CAPL code of this node as defined by the respective diagnostic description.

CANoe will initialize the CAPL callback interface for diagnostics during the call.

**Note**

- This function cannot be used together with [DiagSetTarget](../../Diagnostics/Functions/CAPLfunctionDiagSetTarget.md).
- It cannot be used in a test module; it must be called from the **on preStart** handler.

## Parameters

- **ecuQualifier**: Qualifier of the ECU as set in the diagnostic configuration dialog for the respective diagnostic description.

## Return Values

On success 0, otherwise a value less than 0.

## Example

```plaintext
on preStart
{
   char ecuQual[10] = "KLineECU";
   write( "DiagInitEcuSimulation( %s): %d", ecuQual, DiagInitEcuSimulation(ecuQual));
}
```

[Diagnostics: Connection of the Communication Layer](../../Diagnostics/CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
