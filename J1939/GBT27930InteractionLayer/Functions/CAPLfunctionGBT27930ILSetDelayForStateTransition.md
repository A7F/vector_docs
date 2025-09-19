[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILSetDelayForStateTransition.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_SetDelayForStateTransition**

# GBT27930IL_SetDelayForStateTransition

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GBT27930IL_SetDelayForStateTransition(dword stateTransition, dword delay); // form 1
long GBT27930IL_SetDelayForStateTransition(dbNode node , dword stateTransition, ddword delay); // form 2
```

## Description

Defines delay for a state transition.

## Parameters

- **stateTransition**: State transition to be delayed. The following values are defined:
  - **11**: After the K3 and K4 are closed (resp. GBT27930IL_StartChargingSimulation() is called): Start sending of CHM
  - **0**:
    - Charger: After the appearance of the BHM: Stop sending of CHM and start sending of CRM (BMS is not recognized)
    - BMS: After the appearance of the CHM: Start sending of BHM
  - **1**:
    - Charger: After the appearance of the BRM: Stop sending of CRM (BMS is not recognized) and start sending of CRM (BMS is recognized)
    - BMS: After the appearance of the CRM (BMS is not recognized): Stop sending of BHM and start sending of BRM
  - **2**:
    - Charger: After the appearance of the BCP: Stop sending of CRM (BMS is recognized) and start sending of CML
    - BMS: After the appearance of the CRM (BMS is recognized): Stop sending of BRM and start sending of BCP
  - **3**:
    - Charger: After the appearance of the BRO (Ready for charging): Stop sending of CML and start sending of CRO (Not ready for charging)
    - BMS: After the appearance of the CML: Stop sending of BCP and start sending of BRO (Not ready for charging)
  - **4**:
    - Charger: After the sending of CRO (Not ready for charging) is started: Stop sending of CRO (Not ready for charging) and start sending of CRO (Ready for charging)
    - BMS: After the sending of BRO (Not ready for charging) is started: Stop sending of BRO (Not ready for charging) and start sending of BRO (Ready for charging)
  - **5**:
    - Charger: After the appearance of the BCS: Stop sending of CRO (Ready for charging) and start sending of CCS
    - BMS: After the appearance of the CRO (Not ready for charging): Stop sending of BRO (Ready for charging) and start sending of BCL
  - **15**:
    - BMS: After the sending of BCL is started: In addition to sending BCL, start sending BCS
  - **6**:
    - Charger: After the appearance of the BST: Stop sending of CCS and start sending of CST. This is used when the BMS suspends charging.
    - BMS: After the appearance of the CCS: In addition to sending BCL and BCS, start sending BSM. If configured, BMV and BMT are also sent.
  - **16**:
    - BMS: After the appearance of the CST: Stop sending of BST and start sending of BSD. This is used when the BMS suspends charging.
  - **7**:
    - Charger: After the appearance of the BSD: Stop sending of CST and start sending of CSD
    - BMS: After the appearance of the CST: Stop sending of BCL, BCS and BSM and start sending of BST. This is used when the Charger suspends charging.
  - **8**:
    - Charger: After the sending of the CSD is started: Stop sending of CSD, end of charging
    - BMS: After the sending of the BST is started: Stop sending of BST and start sending of BSD. This is used when the Charger suspends charging.
  - **9**:
    - BMS: After the sending of the BSD is started: Stop sending of BSD, end of charging

- **delay**: Time (in ms) for which the state transition is to be delayed.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: on success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
variables
{
  enum DelayTransition
  {
    chm_to_bhm              = 0,
    crmNotRecognized_to_brm = 1,
    crmRecognized_to_bcp    = 2,
    cml_to_broNotReady      = 3,
    broNotReady_to_broReady = 4,
    croReady_to_bcl         = 5,
    bcl_to_bcl_bcs          = 15,
    ccs_to_bcl_bcs_bsm      = 6,
    cst_to_bsd              = 16,//BMS suspends charging
    cst_to_bst              = 7, //Charger suspends charging
    bst_to_bsd              = 8, //Charger suspends charging
    bsd_to_end              = 9
  }
}

on start
{
  GBT27930IL_InitAsBMS();
  GBT27930IL_SetDelayForStateTransition(chm_to_bhm,              500);
  GBT27930IL_SetDelayForStateTransition(crmNotRecognized_to_brm, 500);
  GBT27930IL_SetDelayForStateTransition(crmRecognized_to_bcp,    500);
  GBT27930IL_SetDelayForStateTransition(cml_to_broNotReady,      500);
  GBT27930IL_SetDelayForStateTransition(broNotReady_to_broReady, 500);
  GBT27930IL_SetDelayForStateTransition(croReady_to_bcl,         500);
  GBT27930IL_SetDelayForStateTransition(bcl_to_bcl_bcs,          500);
  GBT27930IL_SetDelayForStateTransition(ccs_to_bcl_bcs_bsm,      500);
  GBT27930IL_SetDelayForStateTransition(cst_to_bsd,              500);
  GBT27930IL_SetDelayForStateTransition(cst_to_bst,              500);
  GBT27930IL_SetDelayForStateTransition(bst_to_bsd,              500);
  GBT27930IL_SetDelayForStateTransition(bsd_to_end,              500);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
