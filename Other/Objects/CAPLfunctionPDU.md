[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Objects/CAPLfunctionPDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » PDU

# PDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- **PDU short `<AUTOSAR short header ID>` `<PDU var>`**  
  Uses a PDU short header ID from the database to create a typed PDU object.

- **PDU long `<AUTOSAR long header ID>` `<PDU var>`**  
  Uses a PDU long header id from the database to create a typed PDU object.

- **PDU `<AUTOSAR header ID>` `<PDU var>`**  
  Uses a PDU header ID from the database to create a typed PDU object. Only works if header ID is unambiguously.

- **PDU `<AUTOSAR PDU name>` `<PDU var>`**  
  Uses a symbolic PDU name from the database to create a typed PDU object.

- **PDU * `<PDU var>`**  
  Create a type free PDU. A type free PDU can be used for example as a generic function parameter. A type free PDU has limited selectors. A type free PDU can only be sent when a typed PDU is assigned to it.

## Description

Can be used to create a PDU object. The object data can be manipulated via the object's selectors. Additional object properties can be read from the selectors.

A PDU object can be sent using the [TriggerPDU](../Functions/CAPLfunctionTriggerPDU.md) function.

## Parameters

- `<PDU var>`: String that specifies the variable name of the object.

## Selectors

- **BusType**: Bus system of the PDU.  
  - **Value**:  
    - `-1`: eWildcard  
    - `1`: eCAN  
    - `2`: eFlexRay  
    - `3`: eEthernet  
    - `4`: eAdfx  
    - `5`: eLIN  
  - **Type**: enum busType  
  - **Access Limitation**: Read only

- **MsgChannel**: Channel of the PDU.  
  - **Type**: dword  
  - **Access Limitation**: Read only

- **Time / Time_ns**: Time stamp synchronized with the global time base on the computer (hardware or computer system clock).  
  - **Type**: int64  
  - **Access Limitation**: Read only

- **Dir**: Direction of the PDU (Tx or Rx).  
  - **Value**:  
    - `0`: Rx  
    - `1`: Tx  
    - `2`: TxRequest  
  - **Type**: dword  
  - **Access Limitation**: Read only

- **Simulated**: Flag to indicate if this PDU is a simulated PDU (i.e. was send via a simulation node).  
  - **Type**: byte  
  - **Access Limitation**: Read only

- **Name**: Symbolic Name of the PDU.  
  - **Type**: char[]  
  - **Access Limitation**: Read only

- **ShortHeaderID**: Short header ID of the PDU.  
  - **Type**: dword  
  - **Access Limitation**: Read only

- **LongHeaderID**: Long header ID of the PDU.  
  - **Type**: dword  
  - **Access Limitation**: Read only

- **PDUSize**: Buffer size for the reception of the PDU Payload. The size can only be defined at creation of a PDU object.  
  - **Type**: dword  
  - **Access Limitation**: Read only

- **PDULength**: Length of the PDU Payload data.  
  - **Type**: dword  
  - **Access Limitation**: Read only

- **byte(index), word(index), dword(index), qword(index), char(index), int(index), long(index), int64(index), `<signal name>`**: Direct access to the payload/data of the PDU.  
  - **Access Limitation**: Read only

- **UpdateBit**:  
  - **Value**:  
    - `-1`: Unavailable (not configured in the database)  
    - `0`: Unset  
    - `1`: Set  
  - **Type**: long  
  - **Access Limitation**: Read only

- **Payload**: This selector allows the access of the payload array (for using as a byte array parameter in functions).  
  - **Type**: PDUPayload  
  - **Access Limitation**: Read only

- **ValidationFlags**: Flag to indicate the result of the validation process.  
  - **Value**:  
    - `0x0`: NotVerified (unknown, security inactive, pdu has not been verified)  
    - `0x1`: VerificationFalse (verification executed -> verification failed -> PDU is invalid)  
    - `0x3`: VerificationOK (verification executed -> verification successful -> PDU is valid)  
    - `0x8`: ModuleError (internal module error)  
  - **Type**: dword  
  - **Access Limitation**: Read only

- **IsContained**: Determines if the PDU was transmitted within a container.  
  - **Type**: byte  
  - **Access Limitation**: Read only

- **AutosarPDUType**: AUTOSAR PDU type of the PDU.  
  - **Value**:  
    - `0`: ePDUTypeUndefined  
    - `1`: eSignal_I_PDU  
    - `2`: eNM_PDU  
    - `3`: eN_PDU  
    - `4`: eMultiplexed_I_PDU  
    - `5`: eXCP_PDU  
    - `6`: eContainer_I_PDU  
    - `7`: eDCIM_PDU  
    - `8`: eUser_Defined_I_PDU  
    - `9`: eGeneral_Purpose_PDU  
    - `10`: eGeneral_Purpose_I_PDU  
  - **Type**: enum asrPduType  
  - **Access Limitation**: Read only

- **IsSecured**: Enum to indicate if security information are available in the database.  
  - **Value**:  
    - `0`: ePDUnotSecured  
    - `1`: ePDUisSecured  
    - `2`: ePDUinSecuredContainer  
  - **Type**: enum pduSecuredStateInfo  
  - **Access Limitation**: Read only

## Example

### Example 1

```plaintext
On key 'a'
{
  PDU short 4 myPDU;
  myPDU.signal1 = 25;
  TriggerPDU(myPDU);
}
```

### Example 2

```plaintext
void foo (PDU* parPDU)
{
  // evaluate PDU
}
void example ()
{
  PDU EngineData myPDU;
  foo (myPDU);
}
```

### Example 3

```plaintext
on PDU CAN_1::SOMEPDU1
{
  PDU CAN_2::SOMEPDU1 mypdu2;
  mypdu2.Payload = this.Payload;
  triggerPDU(mypdu2);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
