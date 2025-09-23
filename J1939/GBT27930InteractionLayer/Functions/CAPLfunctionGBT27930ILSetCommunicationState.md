[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILSetCommunicationState.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_SetCommunicationState**

# GBT27930IL_SetCommunicationState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_SetCommunicationState(double newState);` // form 1
- `long GBT27930IL_SetCommunicationState(dbNode node, double newState);` // form 2

## Description

Defines the new state of charging communication.

## Parameters

- **newState**: New state of charging communication. The following values are possible:
  - **0**: Waiting for start of charging
  - **20**: Delayed start of CHM is initiated
  - **1**: Sending of CHM
  - **2**: Sending of CHM; delayed start of CRM (BMS is not recognized) is initiated
  - **3**: Sending of CRM (BMS is not recognized)
  - **4**: Sending of CRM (BMS is not recognized); delayed start of CRM (BMS is recognized) is initiated
  - **5**: Sending of CRM (BMS is recognized)
  - **6**: Sending of CRM (BMS is recognized); delayed start of CML is initiated
  - **7**: Sending of CML
  - **8**: Sending of CML; delayed start of CRO (Not ready for charging) is initiated
  - **9**: Sending of CRO (Not ready for charging); delayed start of CRO (Ready for charging) is initiated
  - **10**: Sending of CRO (Ready for charging)
  - **11**: Sending of CRO (Ready for charging); delayed start of CCS is initiated
  - **30**: Sending of BCL
  - **31**: Sending of BCL; delayed start of BCS is initiated
  - **12**: Sending of CCS
  - **13**: Sending of CCS; delayed start of CST is initiated. Is skipped when BMS initializes the end of charging.
  - **14**: Sending of CST
  - **15**: Sending of CST; delayed start of CSD is initiated
  - **16**: Sending of CSD; delayed stop of CSD is initiated
  - **17**: End of charging
  - **18**: —
  - **19**: End of charging
  - **20**: —
  - **50**: Sending of CEM

- **node**: Simulation node to apply the function.

## Return Values

- **0**: on success
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
