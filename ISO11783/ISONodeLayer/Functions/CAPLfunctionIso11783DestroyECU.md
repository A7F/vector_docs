[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783DestroyECU.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783DestroyECU

# Iso11783DestroyECU

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783DestroyECU( dword ecuHandle );
```

## Description

This function deletes a logical node that was generated with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md) from the network.

**Important Note**  
You should avoid allowing this function to be called within a CAPL callback function, since otherwise data consistency of the node layer could be violated.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

- **0**: ECU was correctly deleted
- **1**: ECU couldn't be deleted, because the function was called from a callback
- **2**: invalid ECU handle

## Example

```plaintext
Iso11783DestroyECU(ecuHandle);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
