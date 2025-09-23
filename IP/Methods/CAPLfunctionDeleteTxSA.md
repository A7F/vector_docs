[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionDeleteTxSA.md)

## EthernetMacsecSecureEntity::DeleteTxSA

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecSecureEntity::DeleteTxSA

**Valid for:** CANoe DE

### Method Syntax

```plaintext
byte EthernetMacsecSecureEntity.DeleteTxSA(EthernetMacsecSCI sci, byte AN);
```

### Description

Deletes a secure association for transmitting.

### Parameters

- **sci**: The secure channel id of the secure channel where this SA is part of.
- **AN**: The secure association number for the SA to be queried.

### Return Values

- **byte**:
  - 1 if the call succeeded, 0 otherwise.
  - The call will fail if:
    - The secure channel referred to by the sci does not exist.
    - The AN is not in range 0..3.
    - The SA referred to by the association number does not exist.

### Example

—
