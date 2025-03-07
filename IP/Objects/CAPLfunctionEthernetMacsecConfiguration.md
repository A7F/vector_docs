[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Objects/CAPLfunctionEthernetMacsecConfiguration.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » EthernetMacsecConfiguration

# EthernetMacsecConfiguration

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

EthernetMacsecConfiguration <variable name>;

## Method Syntax

- [EthernetMacsecConfiguration::GetCAK](../Methods/CAPLfunctionGetCAK.md)
- [EthernetMacsecConfiguration::GetCipherSuites](../Methods/CAPLfunctionGetCipherSuites.md)
- [EthernetMacsecConfiguration::GetCKN](../Methods/CAPLfunctionGetCKN.md)
- [EthernetMacsecConfiguration::SetCAK](../Methods/CAPLfunctionSetCAK.md)
- [EthernetMacsecConfiguration::SetCipherSuites](../Methods/CAPLfunctionSetCipherSuites.md)
- [EthernetMacsecConfiguration::SetCKN](../Methods/CAPLfunctionSetCKN.md)

## Description

Define a variable of type **EthernetMacsecConfiguration**. The variable must be initialized by accessing the **macsecConfig** selector of a [EthernetPortAccessEntity](CAPLfunctionEthernetPortAccessEntity.md). Validity of a variable of type EthernetMacsecConfiguration can be verified using its selector **isValid**.

All modifications of a EthernetMacsecConfiguration are temporary, that is, the assigned values will replace the values loaded from the security manager profile only while the measurement is running. The security profile in the security manager will stay untouched.

Note that you can not

- Replace a PAE’s EthernetMacsecConfiguration like this:
  - `pae.macsecConfig = otherMacsecConfig;`
  - `pae.macsecConfig = otherPae.macsecConfig;`
  - The selector **pae.macsecConfig** as such is read-only.
- Write to selectors of a EthernetMacsecConfiguration while its PAE is active. Writing to EthernetMacsecConfiguration's selectors means reconfiguring the PAE, which can only be done while it is not running.

## Parameters

- **name**: Variable name

## Selectors

- **isValid**: 1 if the secure entity has been correctly initialized, 0 otherwise
  - Type: byte
  - Access Limitation: Read-only

- **name**: The name of the MACsec port configuration as in the security profile
  - Type: 
  - Access Limitation: 

- **hwPort**: The measurement port this secure entity is associated with
  - Type: ethernetPort
  - Access Limitation: Read-only

- **MacsecMode**: The MACsec operation mode
  - Type: enum EthernetMacsecMode
  - Access Limitation: Read-write

- **MacsecUnprotectedFramesAllowed**: Determines when unprotected (non-MACsec) frames may be sent or received
  - Type: enum EthernetMacsecUnprotectedFramesAllowed
  - Access Limitation: Read-write

- **ReplayProtection**: Replay protection active/deactivated
  - Type: Byte (0/1)
  - Access Limitation: Read-write

- **ReplayWindow**: Replay window size
  - Type: dword
  - Access Limitation: Read-write

- **SCIPort**: The port number to use when forming the secure channel id
  - Type: word
  - Access Limitation: Read-write

- **MKAPriority**: The key server priority of this MKA instance
  - Type: byte
  - Access Limitation: Read-write

- **MKAPolicy**: Determines how the key server or key client roles shall be determined
  - Type: enum EthernetMacsecKeyAgreementPolicy
  - Access Limitation: Read-write

- **SendAnnouncements**: Activates transmission of announcement parameter sets as part of the MKPDUs
  - Type: byte (0/1)
  - Access Limitation: Read-write

- **MKAHelloTime**: The MKA hello time, in milliseconds
  - Type: dword
  - Access Limitation: Read-write

- **MKABoundedHelloTime**: The MKA hello time if DelayProtection is enabled, in milliseconds
  - Type: dword
  - Access Limitation: Read-write

- **DelayProtection**: Enables MACsec/MKA delay protection
  - Type: byte (0/1)
  - Access Limitation: Read-write

- **IncludeICVIndicator**: Enables transmission of the optional ICV indicator parameter set
  - Type: byte (0/1)
  - Access Limitation: Read-write

- **IncludeSCI**: Enables transmission of the Secure Channel Id (SCI). Will set the SC bit of the MACsec TCI.
  - Type: byte (0/1)
  - Access Limitation: Read-write

- **ES**: Enables transmission of the ES (end station) bit in the MACsec TCI. This is exclusive to IncludeSCI=1
  - Type: byte (0/1)
  - Access Limitation: Read-write

- **SAKTimeout**: The timeout after the MKA key server will initiate rekeying, in milliseconds. Zero means **no rekeying**.
  - Type: dword
  - Access Limitation: Read-write

- **SAKMaxPacketNumber**: Packet number after which the MKA key server will initiate rekeying. Used when a non-XPN cipher is in use.
  - Type: dword
  - Access Limitation: Read-write

- **SAKMaxPacketNumberXPN**: Packet number after which the MKA key server will initiate rekeying. Used when a XPN cipher is in use.
  - Type: qword
  - Access Limitation: Read-write

- **SAKMaxPayload**: Maximum number of bytes to be transmitted or received, after which the MKA key server will initiate rekeying. Zero means **no rekeying**.
  - Type: dword
  - Access Limitation: Read-write

## Example

```plaintext
byte ckn[32];
byte cak[32];
qword ciphers[6];
EthernetMacsecConfig cfg;
dword cknLength;
dword cakLength;
dword ciphersLength;
cfg = pae.macsecConfig;
cknLength = cfg.getCKN(ckn);
write("ckn length=%d", cknLength);
for (i=0;i<cknLength;i++)
{
  write("ckn[%d]=0x%02x", i, ckn[i]);
}
cakLength = cfg.getCAK(cak);
write("cak length=%d", cakLength);
for (i=0;i<cakLength;i++)
{
  write("cak[%d]=0x%02x", i, cak[i]);
}
ciphersLength = cfg.getCipherSuites(ciphers);
write("ciphers length=%d", ciphersLength);
for (i=0;i<ciphersLength;i++)
{
  write("ciphers[%d]=0x%016llx", i, ciphers[i]);
}
cfg.MacsecMode = eMacsecModeIntegrityOnly;
```

[See Also](javascript:void(0);)