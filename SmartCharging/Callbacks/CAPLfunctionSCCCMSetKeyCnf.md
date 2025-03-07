[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMSetKeyCnf.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » **SCC_CM_Set_Key_Cnf**

# SCC_CM_Set_Key_Cnf

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
The **Result** code representation (0x01="Success"/0x00="Failure") is according to the Qualcomm specification, which has also been adopted by other PLC-chip manufacturers.

## Function Syntax

```plaintext
void SCC_CM_Set_Key_Cnf ( byte RunId[], byte SourceMacAddress[], dword Result )
```

## Description

The callback is called as soon as a **CM_Set_Key.Cnf** message is received. Further details that are transmitted in this request can be queried with [SCC_SLAC_GetCMSetKeyCnfData](../Functions/CAPLfunctionSCCSLACGetCMSetKeyCnfData.md).

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **Result**: Result code:
  - 0x00 = failure
  - 0x01 = success
  - 0x02-0xFF = reserved

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)