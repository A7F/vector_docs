[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILGetCommunicationState.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_GetCommunicationState**

# GBT27930IL_GetCommunicationState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_GetCommunicationState(); // form 1`
- `long GBT27930IL_GetCommunicationState(dbNode node); // form 2`

## Description

Returns the current state of charging communication.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

Current state of charging communication. The following values are defined:

- **0**: Waiting for start of charging
- **20**: Delayed start of CHM is initiated
- **1**: Sending of CHM; Waiting for the first CHM
- **2**: Sending of CHM; delayed start of CRM (BMS is not recognized) is initiated; Delayed start of BHM is initiated
- **3**: Sending of CRM (BMS is not recognized); Sending of BHM
- **4**: Sending of CRM (BMS is not recognized); delayed start of CRM (BMS is recognized) is initiated; Sending of BHM; delayed start of BRM is initiated
- **5**: Sending of CRM (BMS is recognized); Sending of BRM
- **6**: Sending of CRM (BMS is recognized); delayed start of CML is initiated; Sending of BRM; delayed start of BCP is initiated
- **7**: Sending of CML; Sending of BCP
- **8**: Sending of CML; delayed start of CRO (Not ready for charging) is initiated; Sending of BCP; delayed start of BRO (Not ready for charging) is initiated
- **9**: Sending of CRO (Not ready for charging); delayed start of CRO (Ready for charging) is initiated; Sending of BRO (Not ready for charging); delayed start of BRO (Ready for charging) is initiated
- **10**: Sending of CRO (Ready for charging); Sending of BRO (Ready for charging)
- **11**: Sending of CRO (Ready for charging); delayed start of CCS is initiated; Sending of BRO (Ready for charging); delayed start of BCL is initiated
- **30**: Sending of BCL
- **31**: Sending of BCL; delayed start of BCS is initiated
- **12**: Sending of CCS; Sending of BCL and BCS
- **13**: Sending of CCS; delayed start of CST is initiated. Is skipped when BMS initializes the end of charging; Sending of BCL and BCS, delayed start of BSM is initiated
- **14**: Sending of CST; Sending of BCL, BCS and BSM
- **15**: Sending of CST; delayed start of CSD is initiated; Sending of BCL, BCS and BSM; delayed start of BST is initiated. Is used when Charger initializes the end of charging.
- **16**: Sending of CSD; delayed stop of CSD is initiated; Sending of BST. Is used when BMS initiates the end of charging.
- **17**: End of charging; Sending of BST; delayed start of BSD is initiated
- **18**: Sending of BSD; delayed stop of BSD is initiated
- **19**: End of charging
- **20**: —
- **50**: Sending of CEM; Sending of CEM

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version **18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
