[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIpsecAssociationInit.md)

**CAPL Functions** » **TCP/IP API** » **ipsecAssociationInit**

# ipsecAssociationInit

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
The function is dependent on the selected stack.  
It is not possible to modify the security association database of the operating system TCP/IP stack.

## Function Syntax

```plaintext
long ipsecAssociationInit(IP_Endpoint source, IP_Endpoint destination, char[] protocol, char[] mode, dword spi);
```

## Description

With this function, it is possible to create a security association record. The record gets initialized with the given parameters.  
A security association record is needed to modify the security association database of a network stack.

## Parameters

- **source**: Source endpoint of the security association.
- **destination**: Destination endpoint of the security association.
- **protocol**: The Ipsec protocol of the security association. The following values are possible:
  - **UNSPEC**: 0
  - **ESP**: 1
  - **AH**: 2

  If ESP is selected, the following properties get initialized with the following values:
  - **ahalgorithm**: sha
  - **ahkey**: 0123456789ABCDEF
  - **espalgorithm**: null

  Otherwise, they will be initialized as follows:
  - **ahalgorithm**: sha
  - **ahkey**: 0123456789ABCDEF
  - **espalgorithm**: none

- **mode**: The IPsec mode of the security association. The following values are possible:
  - **ANY**: 0
  - **TRANSPORT**: 1
  - **TUNNEL**: 2

- **spi**: The security parameter index of the security association.

## Return Values

- **>0**: A valid security association record handle.
- **-1**: Failed

## Example

```plaintext
on start
{
  long association;

  // create and init a security association record
  association = ipsecAssociationInit(ip_Endpoint(192.168.1.1), ip_Endpoint(192.168.1.10), "ah", "any", 30000);
  if(association < 0)
  {
    write("failed to create a security association");
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
