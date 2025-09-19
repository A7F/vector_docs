[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783PDDObjectPoolDeactivate.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783PDDObjectPoolDeactivate

# Iso11783PDDObjectPoolDeactivate

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783PDDObjectPoolDeactivate( dword ecuHandle );
```

## Description

The function sends an Object-pool Deactivate message to the Task Controller and disconnects the connection to the Task Controller.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md) beforehand or ZERO for general parameters.

## Return Values

[Error code](../CAPLfunctionsISONLErrorCodesPDDOnError.md)

## Example

```plaintext
if (Iso11783PDDObjectPoolDeactivate(ecuHandle) == 0) {
  write("Node has disconnected from the Task Controller");
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
